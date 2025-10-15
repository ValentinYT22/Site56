{
  "project": "AdamMM – aplicație de streaming muzical (dark theme)",
  "brand_personality": ["urban", "edgy", "profesionist", "autentic românesc", "energie hip‑hop"],
  "goals": {
    "primary": [
      "Redare rapidă – play din orice listă sau căutare",
      "Gestionare colecții – playlist & favorite",
      "Descoperire – căutare + filtrare rapidă",
      "Player robust – 50+ melodii, seek, volum, shuffle, repeat"
    ],
    "success_metrics": ["timp pănă la prima redare < 7s", "număr playlisturi create", "% piese salvate la favorite", "căutări/ sesiune"]
  },
  "audience": ["fani hip‑hop/rap românesc", "ascultători de muzică pe mobil", "power users care folosesc dark mode"],

  "design_style": {
    "mode": "Dark premium, fără purple/pink gradiente saturate",
    "fusion": "Layout tip Swiss Grid + accente neon (emerald/teal/cyan) + micro‑interacțiuni inspirate din console DJ",
    "style_tags": ["dark", "glass accent limitat", "neon glow subtil", "asymmetrical/bento sections"],
    "imagery_mood": "scene nocturne, lumini de club, vibe urban",
    "motion": "fluid, scurt (150–220ms), easing cubic-bezier(0.2,0.8,0.2,1)"
  },

  "typography": {
    "fonts": {
      "headings": "Space Grotesk",
      "body": "Inter",
      "brand_display_optional": "Bebas Neue (pentru logo/headinguri promo)"
    },
    "install_instructions": [
      "Adaugă în index.html Google Fonts: Space Grotesk, Inter, (opțional) Bebas Neue",
      "Setează în tailwind.config.js theme.fontFamily: { heading: ['Space Grotesk', 'system-ui', 'sans-serif'], body: ['Inter','system-ui','sans-serif'] }"
    ],
    "scale": {
      "h1": "text-4xl sm:text-5xl lg:text-6xl tracking-tight font-semibold",
      "h2": "text-base sm:text-lg font-semibold text-foreground/90",
      "body": "text-sm sm:text-base leading-relaxed",
      "small": "text-xs text-foreground/70"
    },
    "usage": [
      "Titluri playlist/sectiuni: Space Grotesk semibold",
      "Descrieri, meta, timp: Inter regular/medium",
      "Bebas Neue numai pentru bannere/splash/cover artist"
    ]
  },

  "color_system": {
    "note": "Folosește HSL tokens din src/index.css. Mai jos propuneri pentru dark theme adaptate hip‑hop. Respectă Gradient Restriction Rule.",
    "palette_core": {
      "bg": "#0B0C0E",
      "surface": "#111217",
      "surface-2": "#151821",
      "border": "#23262F",
      "foreground": "#F5F7FA",
      "muted": "#9CA3AF"
    },
    "accents": {
      "emerald": "#19F1A6",
      "teal": "#00C2D8",
      "cyan": "#37E0FF",
      "red": "#FF375F"
    },
    "semantic": {
      "primary": "emerald",
      "secondary": "teal",
      "accent": "cyan",
      "destructive": "red",
      "success": "#16A34A",
      "warning": "#F59E0B",
      "info": "#0EA5E9"
    },
    "map_to_tailwind_variables": {
      "--background": "225 16% 5%",
      "--foreground": "210 25% 97%",
      "--card": "225 16% 7%",
      "--card-foreground": "210 25% 97%",
      "--popover": "225 16% 7%",
      "--popover-foreground": "210 25% 97%",
      "--primary": "156 90% 53%", 
      "--primary-foreground": "220 20% 5%",
      "--secondary": "188 74% 44%",
      "--secondary-foreground": "210 25% 97%",
      "--accent": "193 100% 62%",
      "--accent-foreground": "220 20% 5%",
      "--muted": "220 12% 56%",
      "--muted-foreground": "220 12% 70%",
      "--border": "220 15% 18%",
      "--input": "220 15% 18%",
      "--ring": "156 90% 53%",
      "--radius": "0.75rem"
    },
    "gradients_allowed": [
      {
        "name": "Neon Mist",
        "colors": ["#0B0C0E 0%", "#0E1016 40%", "#0B0C0E 100%"],
        "usage": "secțiuni mari de fundal/hero. max 20% viewport"
      },
      {
        "name": "Teal→Emerald soft",
        "colors": ["#00C2D8", "#19F1A6"],
        "usage": "accent de secțiune (nu pe text) și panou artist. Low alpha overlay"
      }
    ],
    "shadows_glow": {
      "soft_neon": "0 0 0 1px rgba(25,241,166,0.15), 0 8px 24px -8px rgba(55,224,255,0.25)",
      "card": "0 10px 30px -15px rgba(0,0,0,0.6)"
    }
  },

  "design_tokens_css": {
    "usage": "Poți suprascrie :root .dark din src/index.css cu HSL-urile de mai sus. Nu aplica transition: all.",
    "extra_vars": ":root { --noise-opacity: 0.035; --btn-radius: 10px; --btn-shadow: 0 10px 24px -12px rgba(25,241,166,0.35); --focus-ring: 0 0 0 2px hsl(var(--ring) / 0.65); }"
  },

  "layout": {
    "grid_system": [
      "Container: mx-auto w-full max-w-7xl px-4 sm:px-6 lg:px-8",
      "Mobile-first, 4-col grid: grid grid-cols-4 gap-3 sm:grid-cols-6 md:grid-cols-8 lg:grid-cols-12",
      "Card spacing: p-3 sm:p-4 lg:p-5 with rounded-xl bg-[hsl(var(--card))]"
    ],
    "navigation": {
      "mobile": "Bottom Nav (Tabs) + mini player bar deasupra",
      "desktop": "Sidebar stânga 264px (Library, Playlists, Favorites) + Content + Right queue pane (lg)",
      "components": ["./components/ui/tabs", "./components/ui/menubar", "./components/ui/scroll-area", "./components/ui/sheet"]
    },
    "pages": {
      "Home": ["Hero artist (cover + CTA play shuffle)", "secțiuni bento: Top Tracks, Albume, Playlisturi Fan", "carusel orizontal pentru recomandări"],
      "Search": ["Command palette full-screen pe mobil", "filtre: gen, an, featuring", "rezultate pe grupuri: Piese, Albume, Playlisturi"],
      "Library": ["Playlists, Favorite, Ascultate Recent"],
      "NowPlaying": ["player full-screen cu cover mare, slider seek, lyrics (scroll-area)"],
      "Playlist Detail": ["header glass cu artă + acțiuni (play, shuffle, edit)", "listă piese reorder drag (ulterior)"]
    }
  },

  "components": {
    "library_to_use": "Shadcn/UI din ./components/ui. Fără HTML primitive pentru dropdown/calendar/toast.",
    "component_path": {
      "button": "./components/ui/button",
      "slider": "./components/ui/slider",
      "progress": "./components/ui/progress",
      "tabs": "./components/ui/tabs",
      "command": "./components/ui/command",
      "dialog": "./components/ui/dialog",
      "dropdown": "./components/ui/dropdown-menu",
      "sheet": "./components/ui/sheet",
      "scroll_area": "./components/ui/scroll-area",
      "card": "./components/ui/card",
      "skeleton": "./components/ui/skeleton",
      "tooltip": "./components/ui/tooltip",
      "switch": "./components/ui/switch",
      "avatar": "./components/ui/avatar",
      "badge": "./components/ui/badge",
      "separator": "./components/ui/separator",
      "sonner": "./components/ui/sonner"
    },
    "button_system": {
      "style": "Professional / Corporate pentru control + Iconic pentru play/pause",
      "variants": {
        "primary": "bg-[hsl(var(--primary))] text-[hsl(var(--primary-foreground))] hover:bg-emerald-400/90 focus-visible:outline-none focus-visible:[box-shadow:var(--focus-ring)]",
        "secondary": "bg-[hsl(var(--secondary))]/10 text-foreground hover:bg-[hsl(var(--secondary))]/20 border border-[hsl(var(--border))]",
        "ghost": "bg-transparent hover:bg-white/5 text-foreground"
      },
      "sizes": {"sm": "h-8 px-3", "md": "h-10 px-4", "lg": "h-12 px-6"},
      "shape_tokens": {"--btn-radius": "10px"}
    },

    "key_modules": [
      {
        "name": "PlayerBar",
        "description": "Bară player fixă (bottom pe mobil, bottom + sticky pe desktop). Include cover, titlu, artiști, controale, progres, volum (lg).",
        "ui": ["Slider shadcn pentru seek & volum", "Tooltip pentru shortcut-uri", "Dropdown pentru opțiuni (add to playlist, favorite)"]
      },
      {
        "name": "NowPlayingDrawer",
        "description": "Sheet pe mobil pentru player full-screen, swipe up/down.",
        "ui": ["./components/ui/sheet", "./components/ui/slider", "./components/ui/scroll-area"]
      },
      {
        "name": "SearchCommand",
        "description": "Command palette + input persistent în top.",
        "ui": ["./components/ui/command", "./components/ui/tabs", "./components/ui/badge"]
      },
      {
        "name": "PlaylistList",
        "description": "Listă scrollabilă de playlisturi cu carduri compacte.",
        "ui": ["./components/ui/card", "./components/ui/scroll-area", "./components/ui/skeleton"]
      }
    ]
  },

  "micro_interactions": {
    "rules": [
      "Fără transition: all; doar proprietăți specifice (color, background-color, box-shadow, opacity).",
      "Hover pe card: translateY(-2px) + ring-teal subtile (duration-150)",
      "Play/Pause: micro-scale 0.98 la press + glow de 120ms",
      "Slider thumb: creștere ușoară (scale-105) la focus",
      "Loader pulse pe cover când schimbă piesa (skeleton)"
    ],
    "tailwind_examples": {
      "card_hover": "transition-colors duration-150 hover:bg-white/5",
      "button_hover": "transition-[background-color,box-shadow] duration-150 hover:shadow-[var(--btn-shadow)]",
      "focus": "focus-visible:outline-none focus-visible:[box-shadow:var(--focus-ring)]"
    }
  },

  "audio_player_scaffold_js": {
    "files": [
      {
        "path": "src/hooks/useAudioPlayer.js",
        "snippet": "import { useEffect, useRef, useState, useCallback } from 'react';\n\nexport const useAudioPlayer = (initialQueue = []) => {\n  const audioRef = useRef(new Audio());\n  const [queue, setQueue] = useState(initialQueue);\n  const [index, setIndex] = useState(0);\n  const [state, setState] = useState({ playing: false, duration: 0, current: 0, volume: 0.8, loop: 'off', shuffle: false });\n\n  const load = useCallback((i) => {\n    const track = queue[i];\n    if (!track) return;\n    audioRef.current.src = track.src;\n    audioRef.current.load();\n    setIndex(i);\n  }, [queue]);\n\n  const play = useCallback(() => { audioRef.current.play(); setState(s=>({ ...s, playing: true })); }, []);\n  const pause = useCallback(() => { audioRef.current.pause(); setState(s=>({ ...s, playing: false })); }, []);\n  const seek = useCallback((t) => { audioRef.current.currentTime = t; setState(s=>({ ...s, current: t })); }, []);\n  const setVolume = useCallback((v) => { audioRef.current.volume = v; setState(s=>({ ...s, volume: v })); }, []);\n  const next = useCallback(() => { const n = (index + 1) % queue.length; load(n); play(); }, [index, queue, load, play]);\n  const prev = useCallback(() => { const p = (index - 1 + queue.length) % queue.length; load(p); play(); }, [index, queue, load, play]);\n\n  useEffect(() => { load(0); }, [load]);\n  useEffect(() => {\n    const a = audioRef.current;\n    const onLoaded = () => setState(s=>({ ...s, duration: a.duration || 0 }));\n    const onTime = () => setState(s=>({ ...s, current: a.currentTime }));\n    const onEnd = () => next();\n    a.addEventListener('loadedmetadata', onLoaded);\n    a.addEventListener('timeupdate', onTime);\n    a.addEventListener('ended', onEnd);\n    return () => {\n      a.removeEventListener('loadedmetadata', onLoaded);\n      a.removeEventListener('timeupdate', onTime);\n      a.removeEventListener('ended', onEnd);\n    };\n  }, [next]);\n\n  return { audioRef, queue, setQueue, index, state, load, play, pause, seek, setVolume, next, prev };\n};"
      },
      {
        "path": "src/components/PlayerBar.jsx",
        "snippet": "import { useMemo } from 'react';\nimport { Slider } from './ui/slider';\nimport { Button } from './ui/button';\nimport { Tooltip, TooltipTrigger, TooltipContent, TooltipProvider } from './ui/tooltip';\n\nexport const PlayerBar = ({ meta, controls }) => {\n  const progress = useMemo(() => [controls.state.current], [controls.state.current]);\n  return (\n    <div className=\"fixed bottom-0 inset-x-0 bg-[hsl(var(--card))]/95 backdrop-blur supports-[backdrop-filter]:bg-[hsl(var(--card))]/80 border-t border-[hsl(var(--border))] z-40\" data-testid=\"player-bar\">\n      <div className=\"mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 h-16 flex items-center gap-4\">\n        <img src={meta.cover} alt=\"cover\" className=\"size-10 rounded-md object-cover\"/>\n        <div className=\"min-w-0\">\n          <p className=\"truncate text-sm font-medium\" data-testid=\"player-track-title\">{meta.title}</p>\n          <p className=\"truncate text-xs text-foreground/70\" data-testid=\"player-track-artist\">{meta.artist}</p>\n        </div>\n        <div className=\"flex items-center gap-2 ml-auto\">\n          <TooltipProvider>\n            <Tooltip>\n              <TooltipTrigger asChild>\n                <Button size=\"sm\" variant=\"ghost\" onClick={controls.prev} data-testid=\"player-prev-button\">⏮️</Button>\n              </TooltipTrigger>\n              <TooltipContent>Previous</TooltipContent>\n            </Tooltip>\n          </TooltipProvider>\n          <Button size=\"sm\" className=\"[box-shadow:var(--btn-shadow)]\" onClick={controls.state.playing ? controls.pause : controls.play} data-testid=\"player-toggle-button\">{controls.state.playing ? 'Pause' : 'Play'}</Button>\n          <TooltipProvider>\n            <Tooltip>\n              <TooltipTrigger asChild>\n                <Button size=\"sm\" variant=\"ghost\" onClick={controls.next} data-testid=\"player-next-button\">⏭️</Button>\n              </TooltipTrigger>\n              <TooltipContent>Next</TooltipContent>\n            </Tooltip>\n          </TooltipProvider>\n        </div>\n      </div>\n      <div className=\"mx-auto max-w-7xl px-4 pb-3 -mt-2\">\n        <Slider value={progress} max={controls.state.duration || 0} step={1} onValueChange={(v)=>controls.seek(v[0])} data-testid=\"player-seek-slider\"/>\n      </div>\n    </div>\n  );\n};"
      }
    ]
  },

  "search_and_filters": {
    "search_component": "Command (./components/ui/command)",
    "ux": [
      "Cmd/Ctrl+K deschide căutarea globală",
      "Sugestii tipărite: top songs, albume, playlisturi",
      "Filtru rapid prin badge-uri: #romtrap, #feat, #2020s"
    ],
    "filter_ui": ["Tabs pentru Piese/Albume/Playlisturi", "Dropdown-menu pentru sortări (Recent, Popular, A-Z)"]
  },

  "states_and_empty": {
    "loading": "skeleton pe cover & linii (./components/ui/skeleton)",
    "empty": {
      "playlist": "Card cu mesaj + button primary 'Creează playlist'",
      "search": "Text ghid: ‘Caută piese, albume sau playlisturi AdamMM’"
    },
    "errors": "sonner toast (./components/ui/sonner) cu variant destructive, data-testid=\"toast-error\""
  },

  "images_and_textures": {
    "noise": "overlays cu opacity 0.03–0.05 peste panouri mari",
    "image_urls": [
      { "url": "https://images.unsplash.com/photo-1633982265569-f2252f50c282?crop=entropy&cs=srgb&fm=jpg&q=85", "category": "hero", "description": "vibe concert urban, lumină albastră" },
      { "url": "https://images.unsplash.com/photo-1643819642888-7d6b326a6da0?crop=entropy&cs=srgb&fm=jpg&q=85", "category": "playlist-header", "description": "portret low light, tonuri verzi/neon" },
      { "url": "https://images.unsplash.com/photo-1713735962775-2c1e22bed453?crop=entropy&cs=srgb&fm=jpg&q=85", "category": "section-bg", "description": "crowd în lumină teal, pentru secțiuni bento" },
      { "url": "https://images.pexels.com/photos/2204724/pexels-photo-2204724.jpeg", "category": "hero-alt", "description": "artist la pupitru luminat, neon" }
    ],
    "usage": [
      "Nu aplica gradient peste imagini text-heavy",
      "Folosește overlay solid de #0B0C0E/40 pentru lizibilitate"
    ]
  },

  "accessibility": {
    "contrast": "Respectă WCAG AA (text vs background > 4.5:1)",
    "focus": "Focus vizibil: [box-shadow:var(--focus-ring)]",
    "keyboard": "toate controalele accesibile prin Tab, Space/Enter",
    "reduced_motion": "respectă prefers-reduced-motion: dezactivează animatii grele",
    "hit_targets": ">= 44x44px pentru butoane player"
  },

  "testing_attributes": {
    "rule": "Toate elementele interactive și informaționale critice trebuie să aibă data-testid (kebab-case, rol bazat).",
    "examples": [
      "data-testid=\"player-bar\"",
      "data-testid=\"playlists-section\"",
      "data-testid=\"search-input\"",
      "data-testid=\"filter-dropdown\"",
      "data-testid=\"favorite-toggle-button\"",
      "data-testid=\"toast-error\""
    ]
  },

  "motion_and_parallax": {
    "library": "Framer Motion (opțional)",
    "install": "npm i framer-motion",
    "patterns": [
      "fade+up la intrare pentru carduri (stagger 40ms)",
      "cover hero cu parallax subtil (translateY pe scroll <= 8px)"
    ]
  },

  "libraries": {
    "primary": ["Shadcn/UI (deja în proiect)", "Sonner pentru toast"],
    "optional": ["framer-motion pentru animații", "wavesurfer.js pentru vizualizare waveform (dacă doriți)"]
  },

  "tailwind_utilities_snippets": [
    "Glass accent panel: bg-white/5 backdrop-blur rounded-xl border border-white/10 shadow-[0_10px_30px_-15px_rgba(0,0,0,0.6)]",
    "Neon ring hover: hover:[box-shadow:0_0_0_2px_hsl(var(--ring))]",
    "Mini title: text-sm font-medium text-foreground truncate"
  ],

  "page_scaffolds_js": {
    "home_page": "export default function Home() { return (<div className=\"mx-auto max-w-7xl px-4\" data-testid=\"home-page\"> <section className=\"pt-6 pb-4\"><header className=\"flex items-end justify-between\"><h1 className=\"text-4xl sm:text-5xl font-semibold tracking-tight\">AdamMM</h1></header></section><section className=\"grid grid-cols-4 gap-3 sm:grid-cols-6 md:grid-cols-8 lg:grid-cols-12\" data-testid=\"playlists-section\"> {/* carduri */} </section></div> ); }",
    "search_page": "export default function SearchPage() { return (<div className=\"mx-auto max-w-7xl px-4\" data-testid=\"search-page\"> {/* Command & filtre */} </div> ); }"
  },

  "icons": {
    "rule": "Nu folosi emoji pentru icon-uri. Utilizează Lucide-React sau FontAwesome CDN.",
    "install_lucide": "npm i lucide-react",
    "example": "import { Play, Pause, SkipBack, SkipForward, Heart } from 'lucide-react';"
  },

  "data_model_notes": {
    "track": ["id", "title", "artist", "duration", "src", "cover", "albumId", "liked:boolean"],
    "playlist": ["id", "name", "cover", "tracks: string[]", "createdAt"]
  },

  "rollout_order": [
    "1) Tokeni culoare & fonturi",
    "2) PlayerBar + hook useAudioPlayer.js",
    "3) Home grid + carusele",
    "4) SearchCommand + filtre",
    "5) Playlist & Favorite flows",
    "6) NowPlayingDrawer și lyrics"
  ],

  "instructions_to_main_agent": [
    "Aplică schema de culori din color_system.map_to_tailwind_variables în :root .dark din src/index.css; păstrează variabilele existente unde e compatibil.",
    "Respectă Gradient Restriction Rule: gradiente doar pe fundaluri de secțiune și eroi, niciodată pe zone text heavy.",
    "Folosește DOAR componente din ./components/ui pentru UI avansat (dropdown, dialog, calendar, toast).",
    "Include data-testid pe butoane, linkuri, inputuri, meniuri, mesaje și informații cheie.",
    "Nu alinia global textul la centru. Folosește aliniere naturală stânga în zonele de lectură.",
    "Asigură stări: loading (skeleton), empty, error (sonner).",
    "Nu folosi transition: all; limitează la proprietăți specifice",
    "Testează pe mobil întâi; păstrează bara player vizibilă la scroll."
  ]
}


---
General UI UX Design Guidelines  
    - You must **not** apply universal transition. Eg: `transition: all`. This results in breaking transforms. Always add transitions for specific interactive elements like button, input excluding transforms
    - You must **not** center align the app container, ie do not add `.App { text-align: center; }` in the css file. This disrupts the human natural reading flow of text
   - NEVER: use AI assistant Emoji characters like`🤖🧠💭💡🔮🎯📚🎭🎬🎪🎉🎊🎁🎀🎂🍰🎈🎨🎰💰💵💳🏦💎🪙💸🤑📊📈📉💹🔢🏆🥇 etc for icons. Always use **FontAwesome cdn** or **lucid-react** library already installed in the package.json

 **GRADIENT RESTRICTION RULE**
NEVER use dark/saturated gradient combos (e.g., purple/pink) on any UI element.  Prohibited gradients: blue-500 to purple 600, purple 500 to pink-500, green-500 to blue-500, red to pink etc
NEVER use dark gradients for logo, testimonial, footer etc
NEVER let gradients cover more than 20% of the viewport.
NEVER apply gradients to text-heavy content or reading areas.
NEVER use gradients on small UI elements (<100px width).
NEVER stack multiple gradient layers in the same viewport.

**ENFORCEMENT RULE:**
    • Id gradient area exceeds 20% of viewport OR affects readability, **THEN** use solid colors

**How and where to use:**
   • Section backgrounds (not content backgrounds)
   • Hero section header content. Eg: dark to light to dark color
   • Decorative overlays and accent elements only
   • Hero section with 2-3 mild color
   • Gradients creation can be done for any angle say horizontal, vertical or diagonal

- For AI chat, voice application, **do not use purple color. Use color like light green, ocean blue, peach orange etc**

</Font Guidelines>

- Every interaction needs micro-animations - hover states, transitions, parallax effects, and entrance animations. Static = dead. 
   
- Use 2-3x more spacing than feels comfortable. Cramped designs look cheap.

- Subtle grain textures, noise overlays, custom cursors, selection states, and loading animations: separates good from extraordinary.
   
- Before generating UI, infer the visual style from the problem statement (palette, contrast, mood, motion) and immediately instantiate it by setting global design tokens (primary, secondary/accent, background, foreground, ring, state colors), rather than relying on any library defaults. Don't make the background dark as a default step, always understand problem first and define colors accordingly
    Eg: - if it implies playful/energetic, choose a colorful scheme
           - if it implies monochrome/minimal, choose a black–white/neutral scheme

**Component Reuse:**
	- Prioritize using pre-existing components from src/components/ui when applicable
	- Create new components that match the style and conventions of existing components when needed
	- Examine existing components to understand the project's component patterns before creating new ones

**IMPORTANT**: Do not use HTML based component like dropdown, calendar, toast etc. You **MUST** always use `/app/frontend/src/components/ui/ ` only as a primary components as these are modern and stylish component

**Best Practices:**
	- Use Shadcn/UI as the primary component library for consistency and accessibility
	- Import path: ./components/[component-name]

**Export Conventions:**
	- Components MUST use named exports (export const ComponentName = ...)
	- Pages MUST use default exports (export default function PageName() {...})

**Toasts:**
  - Use `sonner` for toasts"\n  - Sonner component are located in `/app/src/components/ui/sonner.tsx`

Use 2–4 color gradients, subtle textures/noise overlays, or CSS-based noise to avoid flat visuals.
