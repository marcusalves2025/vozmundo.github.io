import { useState, useRef, useEffect } from 'react'
import './App.css'

function App() {
  const [inputText, setInputText] = useState('')
  const [sourceLanguage, setSourceLanguage] = useState('auto')
  const [targetLanguage, setTargetLanguage] = useState('pt-BR')
  const [detectedLanguage, setDetectedLanguage] = useState<string | null>(null)
  const [isTranslating, setIsTranslating] = useState(false)
  const [translatedText, setTranslatedText] = useState('')
  const [isPlaying, setIsPlaying] = useState(false)
  const [isDarkTheme, setIsDarkTheme] = useState(true)
  const [selectedVoice, setSelectedVoice] = useState('default')
  const [speechRate, setSpeechRate] = useState(1)
  const [availableVoices, setAvailableVoices] = useState<SpeechSynthesisVoice[]>([])
  const [audioError, setAudioError] = useState<string | null>(null)
  const [voiceDebugInfo, setVoiceDebugInfo] = useState<string | null>(null)
  const [translationError, setTranslationError] = useState<string | null>(null)
  
  // Referência para controlar a síntese de voz
  const speechSynthesisRef = useRef<SpeechSynthesisUtterance | null>(null)
  
  // Efeito para aplicar o tema
  useEffect(() => {
    document.body.classList.toggle('light-theme', !isDarkTheme)
  }, [isDarkTheme])
  
  // Efeito para carregar as vozes disponíveis
  useEffect(() => {
    // Verificar se a API de síntese de voz está disponível
    if (!window.speechSynthesis) {
      console.error("API de síntese de voz não suportada neste navegador")
      setAudioError("Seu navegador não suporta síntese de voz. Tente usar Chrome, Edge ou Safari.")
      return
    }
    
    const loadVoices = () => {
      const voices = window.speechSynthesis.getVoices()
      console.log("Vozes disponíveis:", voices.length)
      
      let voiceInfo = "Vozes disponíveis:\n"
      voices.forEach((voice, index) => {
        const voiceDetails = `${index+1}. ${voice.name} (${voice.lang}) - ${voice.localService ? 'Local' : 'Remota'}`
        console.log(voiceDetails)
        voiceInfo += voiceDetails + "\n"
      })
      
      if (voices.length > 0) {
        setAvailableVoices(voices)
        setVoiceDebugInfo(voiceInfo)
        setAudioError(null)
      } else {
        setAudioError("Nenhuma voz disponível. Tente recarregar a página ou usar outro navegador.")
        setVoiceDebugInfo("Nenhuma voz disponível no navegador.")
      }
    }
    
    // Carregar vozes iniciais
    loadVoices()
    
    // Configurar evento para quando as vozes forem carregadas
    if (window.speechSynthesis.onvoiceschanged !== undefined) {
      window.speechSynthesis.onvoiceschanged = loadVoices
    }
    
    // Garantir que o speechSynthesis esteja inicializado
    try {
      // Inicializar o speechSynthesis com um texto vazio para garantir que esteja pronto
      const initUtterance = new SpeechSynthesisUtterance('')
      window.speechSynthesis.speak(initUtterance)
      window.speechSynthesis.cancel() // Cancelar imediatamente
    } catch (error) {
      console.error("Erro ao inicializar speechSynthesis:", error)
      setAudioError("Erro ao inicializar o sistema de voz. Tente recarregar a página.")
    }
    
    return () => {
      window.speechSynthesis.onvoiceschanged = null
      // Limpar qualquer síntese de voz pendente
      window.speechSynthesis.cancel()
    }
  }, [])
  
  // Lista expandida de idiomas suportados
  const languages = [
    { code: 'auto', name: 'Detectar idioma' },
    { code: 'af', name: 'Africâner' },
    { code: 'sq', name: 'Albanês' },
    { code: 'am', name: 'Amárico' },
    { code: 'ar', name: 'Árabe' },
    { code: 'hy', name: 'Armênio' },
    { code: 'az', name: 'Azerbaijano' },
    { code: 'eu', name: 'Basco' },
    { code: 'be', name: 'Bielorrusso' },
    { code: 'bn', name: 'Bengali' },
    { code: 'bs', name: 'Bósnio' },
    { code: 'bg', name: 'Búlgaro' },
    { code: 'ca', name: 'Catalão' },
    { code: 'ceb', name: 'Cebuano' },
    { code: 'ny', name: 'Chichewa' },
    { code: 'zh', name: 'Chinês' },
    { code: 'co', name: 'Corso' },
    { code: 'hr', name: 'Croata' },
    { code: 'cs', name: 'Tcheco' },
    { code: 'da', name: 'Dinamarquês' },
    { code: 'nl', name: 'Holandês' },
    { code: 'en', name: 'Inglês' },
    { code: 'eo', name: 'Esperanto' },
    { code: 'et', name: 'Estoniano' },
    { code: 'tl', name: 'Filipino' },
    { code: 'fi', name: 'Finlandês' },
    { code: 'fr', name: 'Francês' },
    { code: 'fy', name: 'Frísio' },
    { code: 'gl', name: 'Galego' },
    { code: 'ka', name: 'Georgiano' },
    { code: 'de', name: 'Alemão' },
    { code: 'el', name: 'Grego' },
    { code: 'gu', name: 'Gujarati' },
    { code: 'ht', name: 'Crioulo Haitiano' },
    { code: 'ha', name: 'Hauçá' },
    { code: 'haw', name: 'Havaiano' },
    { code: 'iw', name: 'Hebraico' },
    { code: 'he', name: 'Hebraico' },
    { code: 'hi', name: 'Hindi' },
    { code: 'hmn', name: 'Hmong' },
    { code: 'hu', name: 'Húngaro' },
    { code: 'is', name: 'Islandês' },
    { code: 'ig', name: 'Igbo' },
    { code: 'id', name: 'Indonésio' },
    { code: 'ga', name: 'Irlandês' },
    { code: 'it', name: 'Italiano' },
    { code: 'ja', name: 'Japonês' },
    { code: 'jw', name: 'Javanês' },
    { code: 'kn', name: 'Canarês' },
    { code: 'kk', name: 'Cazaque' },
    { code: 'km', name: 'Khmer' },
    { code: 'ko', name: 'Coreano' },
    { code: 'ku', name: 'Curdo (Kurmanji)' },
    { code: 'ky', name: 'Quirguiz' },
    { code: 'lo', name: 'Laosiano' },
    { code: 'la', name: 'Latim' },
    { code: 'lv', name: 'Letão' },
    { code: 'lt', name: 'Lituano' },
    { code: 'lb', name: 'Luxemburguês' },
    { code: 'mk', name: 'Macedônio' },
    { code: 'mg', name: 'Malgaxe' },
    { code: 'ms', name: 'Malaio' },
    { code: 'ml', name: 'Malaiala' },
    { code: 'mt', name: 'Maltês' },
    { code: 'mi', name: 'Maori' },
    { code: 'mr', name: 'Marathi' },
    { code: 'mn', name: 'Mongol' },
    { code: 'my', name: 'Birmanês (Myanmar)' },
    { code: 'ne', name: 'Nepalês' },
    { code: 'no', name: 'Norueguês' },
    { code: 'or', name: 'Odia (Oriya)' },
    { code: 'ps', name: 'Pashto' },
    { code: 'fa', name: 'Persa' },
    { code: 'pl', name: 'Polonês' },
    { code: 'pt', name: 'Português' },
    { code: 'pa', name: 'Punjabi' },
    { code: 'ro', name: 'Romeno' },
    { code: 'ru', name: 'Russo' },
    { code: 'sm', name: 'Samoano' },
    { code: 'gd', name: 'Gaélico Escocês' },
    { code: 'sr', name: 'Sérvio' },
    { code: 'st', name: 'Sesotho' },
    { code: 'sn', name: 'Shona' },
    { code: 'sd', name: 'Sindi' },
    { code: 'si', name: 'Cingalês' },
    { code: 'sk', name: 'Eslovaco' },
    { code: 'sl', name: 'Esloveno' },
    { code: 'so', name: 'Somali' },
    { code: 'es', name: 'Espanhol' },
    { code: 'su', name: 'Sundanês' },
    { code: 'sw', name: 'Suaíli' },
    { code: 'sv', name: 'Sueco' },
    { code: 'tg', name: 'Tadjique' },
    { code: 'ta', name: 'Tâmil' },
    { code: 'te', name: 'Télugo' },
    { code: 'th', name: 'Tailandês' },
    { code: 'tr', name: 'Turco' },
    { code: 'uk', name: 'Ucraniano' },
    { code: 'ur', name: 'Urdu' },
    { code: 'ug', name: 'Uigur' },
    { code: 'uz', name: 'Uzbeque' },
    { code: 'vi', name: 'Vietnamita' },
    { code: 'cy', name: 'Galês' },
    { code: 'xh', name: 'Xhosa' },
    { code: 'yi', name: 'Iídiche' },
    { code: 'yo', name: 'Iorubá' },
    { code: 'zu', name: 'Zulu' }
  ]

  // Mapeamento de idiomas para códigos de país (para síntese de voz)
  const languageToVoiceMapping: Record<string, string> = {
    'af': 'af-ZA',
    'ar': 'ar-SA',
    'bg': 'bg-BG',
    'ca': 'ca-ES',
    'cs': 'cs-CZ',
    'da': 'da-DK',
    'de': 'de-DE',
    'el': 'el-GR',
    'en': 'en-US',
    'es': 'es-ES',
    'et': 'et-EE',
    'fi': 'fi-FI',
    'fr': 'fr-FR',
    'he': 'he-IL',
    'hi': 'hi-IN',
    'hr': 'hr-HR',
    'hu': 'hu-HU',
    'id': 'id-ID',
    'is': 'is-IS',
    'it': 'it-IT',
    'ja': 'ja-JP',
    'ko': 'ko-KR',
    'lt': 'lt-LT',
    'lv': 'lv-LV',
    'ms': 'ms-MY',
    'nl': 'nl-NL',
    'no': 'nb-NO',
    'pl': 'pl-PL',
    'pt': 'pt-BR',
    'ro': 'ro-RO',
    'ru': 'ru-RU',
    'sk': 'sk-SK',
    'sl': 'sl-SI',
    'sr': 'sr-RS',
    'sv': 'sv-SE',
    'th': 'th-TH',
    'tr': 'tr-TR',
    'uk': 'uk-UA',
    'vi': 'vi-VN',
    'zh': 'zh-CN'
  }

  // Configurações de voz para tipos de IA
  const aiVoiceSettings = {
    default: { pitch: 1, rate: 1, voiceType: 'default', name: 'IA Padrão', description: 'Voz neutra e equilibrada' },
    ia_natural: { pitch: 1.05, rate: 1, voiceType: 'female', name: 'IA Natural', description: 'Voz humana realista com entonação natural' },
    ia_assistente: { pitch: 1.1, rate: 0.95, voiceType: 'female', name: 'IA Assistente', description: 'Voz clara e prestativa, ideal para instruções' },
    ia_narrador: { pitch: 0.9, rate: 0.9, voiceType: 'male', name: 'IA Narrador', description: 'Voz profunda e envolvente para narrativas' },
    ia_robótica: { pitch: 0.7, rate: 1.1, voiceType: 'male', name: 'IA Robótica', description: 'Voz metálica e artificial com tom sintético' }
  }

  // Função para detectar o idioma do texto
  const detectLanguage = async (text: string) => {
    if (!text.trim()) return null
    
    try {
      // Usando a API LibreTranslate para detecção de idioma
      const response = await fetch('https://libretranslate.de/detect', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          q: text
        })
      })
      
      if (!response.ok) {
        throw new Error(`Erro na API de detecção: ${response.status} ${response.statusText}`)
      }
      
      const data = await response.json()
      
      if (data && data.length > 0 && data[0].language) {
        console.log("Idioma detectado:", data[0].language)
        return data[0].language
      } else {
        throw new Error('Resposta da API não contém idioma detectado')
      }
    } catch (error) {
      console.error("Erro na detecção de idioma:", error)
      return null
    }
  }

  // Função para traduzir texto usando a API LibreTranslate
  const translateText = async (text: string, source: string, target: string) => {
    if (!text.trim()) return ""
    
    // Se o idioma de origem for 'auto', tentamos detectar o idioma primeiro
    let sourceCode = source
    if (source === 'auto') {
      const detectedCode = await detectLanguage(text)
      if (detectedCode) {
        sourceCode = detectedCode
        setDetectedLanguage(detectedCode)
      } else {
        sourceCode = 'en' // Fallback para inglês se não conseguir detectar
        setDetectedLanguage('en')
      }
    } else {
      // Extrair apenas o código de idioma principal (ex: 'pt' de 'pt-BR')
      sourceCode = source.split('-')[0]
    }
    
    // Para o idioma de destino, usamos apenas o código principal (ex: 'pt' de 'pt-BR')
    const targetCode = target.split('-')[0]
    
    // Se os idiomas forem iguais, apenas retornamos o texto original
    if (sourceCode === targetCode) {
      return text
    }
    
    try {
      // Usando a API LibreTranslate (pública)
      const response = await fetch('https://libretranslate.de/translate', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          q: text,
          source: sourceCode,
          target: targetCode,
          format: 'text'
        })
      })
      
      if (!response.ok) {
        throw new Error(`Erro na API: ${response.status} ${response.statusText}`)
      }
      
      const data = await response.json()
      
      if (data.translatedText) {
        return data.translatedText
      } else {
        throw new Error('Resposta da API não contém texto traduzido')
      }
    } catch (error) {
      console.error("Erro na tradução:", error)
      throw error
    }
  }

  // Função para lidar com a tradução
  const handleTranslate = async () => {
    if (!inputText.trim()) return
    
    setIsTranslating(true)
    setTranslationError(null)
    setDetectedLanguage(null)
    
    try {
      // Traduzir o texto usando a API
      const translated = await translateText(inputText, sourceLanguage, targetLanguage)
      setTranslatedText(translated)
    } catch (error) {
      console.error("Erro ao traduzir:", error)
      setTranslationError(`Erro ao traduzir: ${error}. Usando simulação como fallback.`)
      
      // Fallback para simulação em caso de erro
      setTranslatedText(`Texto traduzido (simulado): ${inputText}`)
    } finally {
      setIsTranslating(false)
    }
  }

  // Função para lidar com upload de imagem (OCR)
  const handleImageUpload = (e: React.ChangeEvent<HTMLInputElement>) => {
    const file = e.target.files?.[0]
    if (file) {
      // Aqui seria implementada a lógica de OCR
      // Por enquanto, apenas mostramos o nome do arquivo
      setInputText(`[OCR pendente para o arquivo: ${file.name}]`)
    }
  }

  // Função para encontrar a melhor voz disponível para um idioma específico
  const findBestVoice = (lang: string, voiceType: string) => {
    // Verificar se temos vozes disponíveis
    if (availableVoices.length === 0) {
      console.warn("Nenhuma voz disponível para seleção")
      return null
    }
    
    // Extrair o código de idioma principal (ex: 'pt' de 'pt-BR')
    const mainLang = lang.toLowerCase().split('-')[0]
    
    // Tentar encontrar uma voz exata para o idioma completo (incluindo região)
    let exactVoices = availableVoices.filter(voice => 
      voice.lang.toLowerCase() === lang.toLowerCase()
    )
    
    // Se não encontrar voz exata, tentar pelo código principal
    if (exactVoices.length === 0) {
      exactVoices = availableVoices.filter(voice => 
        voice.lang.toLowerCase().startsWith(mainLang.toLowerCase() + '-')
      )
    }
    
    // Se ainda não encontrar, tentar qualquer voz que contenha o código principal
    if (exactVoices.length === 0) {
      exactVoices = availableVoices.filter(voice => 
        voice.lang.toLowerCase().includes(mainLang.toLowerCase())
      )
    }
    
    // Se encontrou vozes para o idioma, filtrar pelo tipo (feminina/masculina)
    if (exactVoices.length > 0) {
      if (voiceType === 'female') {
        const femaleVoice = exactVoices.find(voice => 
          voice.name.toLowerCase().includes('female') || 
          voice.name.toLowerCase().includes('woman') ||
          voice.name.toLowerCase().includes('girl') ||
          voice.name.toLowerCase().includes('f') ||
          voice.name.toLowerCase().includes('mulher') ||
          voice.name.toLowerCase().includes('feminina')
        )
        if (femaleVoice) return femaleVoice
      }
      
      if (voiceType === 'male') {
        const maleVoice = exactVoices.find(voice => 
          voice.name.toLowerCase().includes('male') || 
          voice.name.toLowerCase().includes('man') ||
          voice.name.toLowerCase().includes('boy') ||
          voice.name.toLowerCase().includes('m') ||
          voice.name.toLowerCase().includes('homem') ||
          voice.name.toLowerCase().includes('masculino')
        )
        if (maleVoice) return maleVoice
      }
      
      // Se não encontrar voz específica do tipo, retorna a primeira disponível para o idioma
      return exactVoices[0]
    }
    
    // Se não encontrar vozes para o idioma específico, tente encontrar para inglês como fallback
    console.warn(`Nenhuma voz encontrada para o idioma ${lang}, usando fallback para inglês`)
    const englishVoices = availableVoices.filter(voice => 
      voice.lang.toLowerCase().includes('en-')
    )
    
    if (englishVoices.length > 0) {
      // Tentar encontrar voz em inglês do tipo especificado
      if (voiceType === 'female') {
        const femaleVoice = englishVoices.find(voice => 
          voice.name.toLowerCase().includes('female') || 
          voice.name.toLowerCase().includes('woman') ||
          voice.name.toLowerCase
(Content truncated due to size limit. Use line ranges to read in chunks)
