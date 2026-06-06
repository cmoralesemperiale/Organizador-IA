<!DOCTYPE html>
<html lang="es" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Routinely AI — Planificador Minimalista</title>
    <!-- Tailwind CSS para el diseño ágil -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter para lectura clara y Outfit para encabezados elegantes -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Outfit:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome para iconografía sobria -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        outfit: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        premium: {
                            black: '#0c0c0e',
                            border: '#1c1c21',
                            accent: '#ffffff',
                            success: '#10b981',
                        }
                    },
                    boxShadow: {
                        'premium': '0 8px 30px rgb(0 0 0 / 0.8)',
                    }
                }
            }
        }
    </script>

    <style>
        /* Ocultar barra de scroll estética */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
        
        /* Transiciones suaves globales */
        * {
            transition-property: background-color, border-color, text-color, fill, stroke, opacity;
            transition-duration: 200ms;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* Estilo base del cuerpo */
        body {
            background-color: #000000;
            color: #e4e4e7;
        }
    </style>
</head>
<body class="h-full font-sans flex flex-col justify-between overflow-x-hidden select-none">

    <!-- CABECERA PRINCIPAL -->
    <header class="border-b border-premium-border/60 bg-black/80 backdrop-blur sticky top-0 z-40 px-4 py-4 md:px-8">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <div class="flex items-center space-x-3">
                <div class="w-8 h-8 rounded-lg bg-zinc-900 border border-premium-border flex items-center justify-center">
                    <span class="font-outfit font-bold text-sm text-white">R</span>
                </div>
                <div>
                    <h1 class="text-sm font-outfit font-semibold tracking-wider text-white">ROUTINELY AI</h1>
                    <p class="text-[10px] text-zinc-500 tracking-tight">Productividad Inteligente & Confort</p>
                </div>
            </div>
            
            <div class="flex items-center space-x-3">
                <span id="currentTimeDisplay" class="text-xs font-mono font-medium text-zinc-400 bg-zinc-950 border border-premium-border/80 px-2.5 py-1 rounded-md">
                    00:00:00
                </span>
            </div>
        </div>
    </header>

    <!-- CONTENIDO CENTRAL -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 md:p-8 space-y-6">
        
        <!-- CARRUSEL DE DÍAS (Fácil selección táctil para móvil) -->
        <div class="space-y-2">
            <span class="text-[9px] font-sans font-bold text-zinc-500 uppercase tracking-widest block">Seleccionar Día de Agenda</span>
            <div class="flex overflow-x-auto space-x-2 pb-2 no-scrollbar snap-x touch-pan-x" id="daysCarousel">
                <!-- Se inyecta dinámicamente con JS -->
            </div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-stretch">
            
            <!-- PANEL IZQUIERDO: FORMULARIOS DE CREACIÓN (Mecánica Manual y Procesamiento Inteligente) -->
            <section class="lg:col-span-5 flex flex-col space-y-6">
                
                <!-- PROCESADOR DE RUTINAS POR INSTRUCCIÓN RÁPIDA (Natural Language) -->
                <div class="bg-premium-black border border-premium-border rounded-xl p-5 shadow-premium space-y-4">
                    <div class="space-y-1">
                        <div class="flex items-center space-x-2">
                            <span class="w-1.5 h-1.5 rounded-full bg-zinc-400"></span>
                            <h3 class="font-outfit font-medium text-xs text-zinc-200 tracking-wider">CREACIÓN POR INSTRUCCIÓN</h3>
                        </div>
                        <p class="text-[10px] text-zinc-500">Escribe tus actividades y horarios de forma libre. Nuestro procesador las organizará por ti.</p>
                    </div>

                    <div class="space-y-3">
                        <textarea id="aiPromptInput" rows="3" 
                            class="w-full bg-zinc-950 border border-premium-border focus:border-zinc-500 rounded-lg p-3 text-xs text-zinc-300 placeholder-zinc-600 focus:outline-none resize-none font-sans"
                            placeholder="Ej: 'Mañana despertar a las 7:30 am, meditar a las 8, trabajar a las 9:30, gimnasio a las 18:00 y leer a las 22:00'"></textarea>
                        
                        <div class="flex items-center justify-between gap-3">
                            <div class="text-[9px] text-zinc-500 flex items-center gap-1.5">
                                <i class="fa-regular fa-lightbulb text-zinc-600"></i>
                                <span>Presiona Procesar para mapear la rutina de inmediato.</span>
                            </div>
                            <button onclick="processNaturalLanguageRoutine()" 
                                class="bg-zinc-100 hover:bg-zinc-200 text-black text-xs font-medium py-2 px-4 rounded-lg transition shrink-0 flex items-center space-x-1.5">
                                <i class="fa-solid fa-wand-magic-sparkles text-[11px]"></i>
                                <span>Procesar</span>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- FORMULARIO MANUAL CLÁSICO (Precisión Absoluta) -->
                <div class="bg-premium-black border border-premium-border rounded-xl p-5 shadow-premium space-y-4">
                    <div class="space-y-1">
                        <div class="flex items-center space-x-2">
                            <span class="w-1.5 h-1.5 rounded-full bg-zinc-400"></span>
                            <h3 class="font-outfit font-medium text-xs text-zinc-200 tracking-wider font-semibold">AGREGAR ACTIVIDAD MANUAL</h3>
                        </div>
                        <p class="text-[10px] text-zinc-500">Planifica con total exactitud tus hábitos, bloques de trabajo o descansos.</p>
                    </div>

                    <form onsubmit="handleManualSubmit(event)" class="space-y-3">
                        <div>
                            <label class="text-[9px] font-sans font-bold text-zinc-500 uppercase tracking-widest block mb-1">Nombre de la Actividad</label>
                            <input type="text" id="manualTitle" required maxlength="50"
                                class="w-full bg-zinc-950 border border-premium-border focus:border-zinc-500 rounded-lg px-3 py-2 text-xs text-zinc-300 placeholder-zinc-600 focus:outline-none"
                                placeholder="Ej: Lectura técnica / Cardio en ayunas">
                        </div>

                        <div class="grid grid-cols-2 gap-3">
                            <div>
                                <label class="text-[9px] font-sans font-bold text-zinc-500 uppercase tracking-widest block mb-1">Hora de Inicio</label>
                                <input type="time" id="manualTime" required
                                    class="w-full bg-zinc-950 border border-premium-border focus:border-zinc-500 rounded-lg px-3 py-2 text-xs text-zinc-350 focus:outline-none">
                            </div>
                            <div>
                                <label class="text-[9px] font-sans font-bold text-zinc-500 uppercase tracking-widest block mb-1">Categoría</label>
                                <select id="manualCategory" 
                                    class="w-full bg-zinc-950 border border-premium-border focus:border-zinc-500 rounded-lg px-3 py-2 text-xs text-zinc-350 focus:outline-none">
                                    <option value="Trabajo">Trabajo</option>
                                    <option value="Estudio">Estudio</option>
                                    <option value="Salud">Salud / Deporte</option>
                                    <option value="Ocio">Descanso / Ocio</option>
                                </select>
                            </div>
                        </div>

                        <button type="submit" 
                            class="w-full bg-zinc-900 hover:bg-zinc-850 text-white border border-premium-border hover:border-zinc-700 font-medium text-xs py-2 px-4 rounded-lg transition flex items-center justify-center space-x-1.5 mt-2">
                            <i class="fa-solid fa-plus text-[10px]"></i>
                            <span>Agregar al Cronograma</span>
                        </button>
                    </form>
                </div>
            </section>

            <!-- PANEL DERECHO: MONITOR DE AGENDA & CRONOGRAMA MINIMALISTA -->
            <section class="lg:col-span-7 flex flex-col space-y-6">
                
                <!-- DASHBOARD DE ENFOQUE & RENDIMIENTO (Sober & Confortable) -->
                <div class="bg-premium-black border border-premium-border rounded-xl p-6 shadow-premium flex flex-col md:flex-row items-center justify-between gap-6 relative overflow-hidden">
                    
                    <div class="space-y-1.5 text-center md:text-left z-10">
                        <div class="flex items-center justify-center md:justify-start space-x-2.5">
                            <span class="w-2 h-2 rounded-full bg-white"></span>
                            <h2 class="text-xs font-outfit font-medium text-zinc-100 uppercase tracking-wider" id="timelineDateHeader">CARGANDO CRONOGRAMA...</h2>
                        </div>
                        <p class="text-[10px] text-zinc-500 font-sans">Monitorea y cumple de manera disciplinada tus tareas.</p>
                        
                        <!-- Panel de Enfoque Activo Sutil -->
                        <div class="pt-2 flex items-center justify-center md:justify-start gap-2" id="currentFocusTaskPanel">
                            <span class="text-[9px] text-zinc-400 font-sans font-bold uppercase tracking-widest bg-zinc-900 px-2 py-0.5 border border-premium-border rounded">SIGUIENTE ACCIÓN:</span>
                            <span class="text-xs text-zinc-350 font-medium" id="currentFocusTaskTitle">No hay tareas programadas</span>
                        </div>
                    </div>

                    <!-- HUD de Progreso Sobrio -->
                    <div class="flex items-center space-x-4 bg-black border border-premium-border px-5 py-4 rounded-xl min-w-[240px] w-full md:w-auto justify-between shadow-sm">
                        <div class="flex flex-col">
                            <span class="text-[9px] text-zinc-500 font-sans font-semibold uppercase tracking-widest">PROGRESO DIARIO</span>
                            <span class="text-xl font-outfit font-semibold text-white mt-1" id="progressPercentage">0%</span>
                            <span class="text-[10px] text-zinc-400 font-sans font-light" id="progressCompletedText">0 de 0 completados</span>
                        </div>
                        
                        <!-- Indicador Circular Minimalista -->
                        <div class="relative w-12 h-12 flex items-center justify-center">
                            <svg class="w-full h-full transform -rotate-90">
                                <circle cx="24" cy="24" r="20" stroke="#18181b" stroke-width="3" fill="transparent" />
                                <circle id="progressCircle" cx="24" cy="24" r="20" stroke="#ffffff" stroke-width="3" fill="transparent" stroke-dasharray="125.6" stroke-dashoffset="125.6" class="transition-all duration-300 ease-out" />
                            </svg>
                            <i class="fa-solid fa-circle-check absolute text-premium-success text-xs hidden" id="trophyIndicator"></i>
                        </div>
                    </div>
                </div>

                <!-- CRONOGRAMA PRINCIPAL -->
                <div class="bg-premium-black border border-premium-border rounded-xl p-6 shadow-premium flex-grow flex flex-col relative min-h-[420px]">
                    <div class="flex items-center justify-between pb-4 border-b border-premium-border/60 mb-6">
                        <div class="space-y-1">
                            <h3 class="text-xs font-outfit font-medium text-white tracking-wider">CRONOGRAMA DE ACTIVIDADES</h3>
                            <p class="text-[10px] text-zinc-500">Cronología ordenada de tus bloques para el día <span id="selectedDayLabel" class="font-semibold text-zinc-400">HOY</span>.</p>
                        </div>
                        <button onclick="clearTimeline()" 
                            class="text-[10px] font-medium text-zinc-400 hover:text-white border border-premium-border hover:border-zinc-700 bg-zinc-950 hover:bg-zinc-900 py-1.5 px-3 rounded-lg transition flex items-center space-x-1.5">
                            <i class="fa-solid fa-trash-can text-[9px] text-zinc-500"></i>
                            <span>Limpiar Todo</span>
                        </button>
                    </div>

                    <!-- LISTA DE ACTIVIDADES (TIMELINE) -->
                    <div class="relative flex-grow flex flex-col justify-between">
                        <!-- Línea vertical decorativa del cronograma -->
                        <div class="absolute left-6 top-1 bottom-1 w-[1px] bg-zinc-900 z-0 hidden" id="timelineVerticalLine"></div>
                        
                        <div id="timelineContainer" class="space-y-3 z-10 relative">
                            <!-- Inyectado dinámicamente con JS -->
                        </div>

                        <!-- Estado Vacío Sobrio -->
                        <div id="timelineEmptyState" class="hidden flex-col items-center justify-center py-20 text-center space-y-3">
                            <div class="w-10 h-10 rounded-full border border-premium-border bg-zinc-950 flex items-center justify-center text-zinc-500">
                                <i class="fa-regular fa-calendar-plus text-sm"></i>
                            </div>
                            <div class="space-y-1 max-w-[280px]">
                                <h4 class="text-xs font-outfit font-semibold text-zinc-300 tracking-wide uppercase">Día despejado</h4>
                                <p class="text-[10px] text-zinc-500 leading-normal">No hay actividades planificadas para este día. Escribe una instrucción arriba o añade una tarea manualmente.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- CONTENEDOR DE NOTIFICACIONES TOAST (Sutiles y profesionales) -->
    <div id="toastContainer" class="fixed bottom-6 right-6 z-50 flex flex-col space-y-2 pointer-events-none max-w-sm w-full px-4 md:px-0">
        <!-- Inyectado mediante JS -->
    </div>

    <!-- PIE DE PÁGINA -->
    <footer class="border-t border-premium-border/40 py-6 px-4 md:px-8 mt-12">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between text-[10px] text-zinc-600 space-y-2 sm:space-y-0">
            <p>© 2026 Routinely AI. Pensado para el enfoque sobrio, ordenado y el máximo confort diario.</p>
            <div class="flex items-center space-x-4">
                <span>Almacenamiento Local Activo (Privado)</span>
                <span class="w-1.5 h-1.5 rounded-full bg-emerald-500"></span>
            </div>
        </div>
    </footer>

    <!-- COMPONENTE SCRIPT - LÓGICA E INTERACTIVIDAD INTEGRAL -->
    <script>
        // CONFIGURACIÓN DE BASE DE DATOS Y ESTADOS LOCALES
        const STORAGE_KEY = "RoutinelyAI_UserRoutines_v2";
        let userRoutines = {}; // Estructura: { 'YYYY-MM-DD': [ { id, time, title, category, completed }, ... ] }
        
        let daysArray = [];
        let selectedDayIndex = 0; // Por defecto: 0 (Hoy)

        // AUDIO CONTEXT - SÍNTESIS DE TONOS PREMIUM DE CONFIRMACIÓN (No ruidoso, tipo Apple/Notion)
        let audioCtx = null;
        function initAudio() {
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
        }

        // Tono sofisticado doble para el "Check" exitoso
        function playSuccessChime() {
            try {
                initAudio();
                if (!audioCtx) return;

                const now = audioCtx.currentTime;
                
                // Primer tono (Fundamental)
                const osc1 = audioCtx.createOscillator();
                const gain1 = audioCtx.createGain();
                osc1.type = 'sine';
                osc1.frequency.setValueAtTime(523.25, now); // C5
                osc1.frequency.exponentialRampToValueAtTime(659.25, now + 0.12); // E5
                
                gain1.gain.setValueAtTime(0.08, now);
                gain1.gain.exponentialRampToValueAtTime(0.001, now + 0.3);
                
                osc1.connect(gain1);
                gain1.connect(audioCtx.destination);
                osc1.start(now);
                osc1.stop(now + 0.3);

                // Segundo tono armonizado sutilmente retrasado
                setTimeout(() => {
                    if (!audioCtx) return;
                    const osc2 = audioCtx.createOscillator();
                    const gain2 = audioCtx.createGain();
                    osc2.type = 'sine';
                    osc2.frequency.setValueAtTime(783.99, audioCtx.currentTime); // G5
                    osc2.frequency.exponentialRampToValueAtTime(1046.50, audioCtx.currentTime + 0.15); // C6
                    
                    gain2.gain.setValueAtTime(0.06, audioCtx.currentTime);
                    gain2.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.4);
                    
                    osc2.connect(gain2);
                    gain2.connect(audioCtx.destination);
                    osc2.start(audioCtx.currentTime);
                    osc2.stop(audioCtx.currentTime + 0.4);
                }, 75);

            } catch (e) {
                console.warn("Audio Context bloqueado o no soportado por políticas de navegador.", e);
            }
        }

        // Tono sutil al completar el 100% de la agenda diaria (Fanfarria cálida)
        function playCompleteDayFanfare() {
            try {
                initAudio();
                if (!audioCtx) return;
                const now = audioCtx.currentTime;

                const chords = [329.63, 392.00, 523.25, 659.25]; // Acorde mayor Mi-Sol-Do-Mi (C Major chord de confort)
                chords.forEach((freq, idx) => {
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    osc.type = 'triangle'; // Sonido más cálido y analógico
                    osc.frequency.setValueAtTime(freq, now + (idx * 0.05));
                    
                    gain.gain.setValueAtTime(0.05, now + (idx * 0.05));
                    gain.gain.exponentialRampToValueAtTime(0.001, now + 0.6);
                    
                    osc.connect(gain);
                    gain.connect(audioCtx.destination);
                    osc.start(now + (idx * 0.05));
                    osc.stop(now + 0.7);
                });
            } catch (e) {
                console.warn(e);
            }
        }

        // GENERACIÓN DE LOS 7 DÍAS CONSECUTIVOS (Desde Hoy en adelante)
        function generateDaysArray() {
            const tempDays = [];
            const daysNames = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
            const today = new Date();

            for (let i = 0; i < 7; i++) {
                const targetDate = new Date(today);
                targetDate.setDate(today.getDate() + i);

                const yyyy = targetDate.getFullYear();
                const mm = String(targetDate.getMonth() + 1).padStart(2, '0');
                const dd = String(targetDate.getDate()).padStart(2, '0');
                
                const dateString = `${yyyy}-${mm}-${dd}`;
                const dayName = daysNames[targetDate.getDay()];
                const dayNumber = targetDate.getDate();
                const shortMonth = targetDate.toLocaleString('es-ES', { month: 'short' });

                tempDays.push({
                    index: i,
                    dateString: dateString,
                    dayOfWeek: dayName,
                    shortDate: `${dayNumber} ${shortMonth}`,
                    dayLabel: i === 0 ? "Hoy" : (i === 1 ? "Mañana" : dayName)
                });
            }
            daysArray = tempDays;
        }

        // RENDERIZADO VISUAL DEL SELECCIONADOR DE DÍAS (CARRUSEL TÁCTIL)
        function renderDaysCarousel() {
            const container = document.getElementById('daysCarousel');
            if (!container) return;

            container.innerHTML = '';
            daysArray.forEach(day => {
                const isSelected = day.index === selectedDayIndex;
                
                const button = document.createElement('div');
                button.id = `dayBtn_${day.index}`;
                
                // Clases CSS base y de estado activo (Ultra sobrio)
                if (isSelected) {
                    button.className = "snap-center shrink-0 w-24 py-3 px-2 rounded-xl bg-zinc-100 text-black font-sans font-semibold text-center transition border border-transparent";
                } else {
                    button.className = "snap-center shrink-0 w-24 py-3 px-2 rounded-xl bg-premium-black hover:bg-zinc-900 text-zinc-450 hover:text-zinc-200 font-sans text-center transition border border-premium-border cursor-pointer";
                }

                button.innerHTML = `
                    <p class="text-[9px] uppercase tracking-widest ${isSelected ? 'text-zinc-600' : 'text-zinc-500'} font-medium">${day.dayLabel}</p>
                    <p class="text-sm font-outfit mt-0.5">${day.shortDate}</p>
                `;

                button.onclick = () => selectDay(day.index);
                container.appendChild(button);
            });
        }

        // CAMBIO ACTIVO DE DÍA EN LA INTERFAZ
        function selectDay(index) {
            selectedDayIndex = index;
            
            // Actualizar estilo visual en el carrusel
            daysArray.forEach(day => {
                const el = document.getElementById(`dayBtn_${day.index}`);
                if (el) {
                    if (day.index === index) {
                        el.className = "snap-center shrink-0 w-24 py-3 px-2 rounded-xl bg-zinc-100 text-black font-sans font-semibold text-center transition border border-transparent";
                    } else {
                        el.className = "snap-center shrink-0 w-24 py-3 px-2 rounded-xl bg-premium-black hover:bg-zinc-900 text-zinc-450 hover:text-zinc-200 font-sans text-center transition border border-premium-border cursor-pointer";
                    }
                }
            });

            const dayObj = daysArray[index];
            document.getElementById('selectedDayLabel').innerText = dayObj.dayLabel.toUpperCase();
            
            let headerText = `Agenda: ${dayObj.dayOfWeek}`;
            if (index === 0) headerText = "Agenda de Hoy";
            if (index === 1) headerText = "Agenda de Mañana";
            
            document.getElementById('timelineDateHeader').innerText = `${headerText} // ${dayObj.shortDate.toUpperCase()}`;
            
            renderTimeline();
            updateDailyProgress();
            updateDashboardFocusElement();
        }

        // PRE-POBLAR RUTINAS MOCK (Sugerencias inteligentes iniciales para que el usuario aprecie la app vacía)
        function initializeMockRoutines() {
            const raw = localStorage.getItem(STORAGE_KEY);
            if (raw) {
                try {
                    userRoutines = JSON.parse(raw);
                    return;
                } catch (e) {
                    console.error("Error cargando localStorage corrupto, reiniciando...", e);
                }
            }

            // Población por defecto para Hoy y Mañana si no hay datos almacenados
            generateDaysArray();
            const todayStr = daysArray[0].dateString;
            const tomorrowStr = daysArray[1].dateString;

            userRoutines = {};
            
            // Agenda base de Hoy
            userRoutines[todayStr] = [
                { id: "mock1", time: "07:30", title: "Rutina matinal & Hidratación consciente", category: "Salud", completed: true },
                { id: "mock2", time: "09:00", title: "Bloque de enfoque profundo: Trabajo clave", category: "Trabajo", completed: false },
                { id: "mock3", time: "14:00", title: "Caminata al aire libre & Desconexión digital", category: "Salud", completed: false },
                { id: "mock4", time: "16:30", title: "Revisión de métricas e informes de avance", category: "Trabajo", completed: false },
                { id: "mock5", time: "22:00", title: "Lectura de literatura de desarrollo profesional", category: "Estudio", completed: false }
            ];

            // Agenda base de Mañana
            userRoutines[tomorrowStr] = [
                { id: "mockt1", time: "08:00", title: "Meditación guiada & Movilidad articular", category: "Salud", completed: false },
                { id: "mockt2", time: "10:00", title: "Alineación de objetivos de equipo y planificación", category: "Trabajo", completed: false },
                { id: "mockt3", time: "17:00", title: "Sesión de estudio: Nuevas metodologías", category: "Estudio", completed: false },
                { id: "mockt4", time: "21:30", title: "Desconexión progresiva de pantallas electrónicas", category: "Ocio", completed: false }
            ];

            saveToLocalStorage();
        }

        function saveToLocalStorage() {
            localStorage.setItem(STORAGE_KEY, JSON.stringify(userRoutines));
        }

        // DETECCIÓN DE SIGUIENTE ACCIÓN / TAREA EN ENFOQUE
        function updateDashboardFocusElement() {
            const selectedDay = daysArray[selectedDayIndex];
            const tasks = userRoutines[selectedDay.dateString] || [];
            const focusPanel = document.getElementById('currentFocusTaskPanel');
            const focusTitle = document.getElementById('currentFocusTaskTitle');

            if (tasks.length === 0) {
                focusTitle.innerText = "Día libre de pendientes programados";
                return;
            }

            // Buscar la primera tarea pendiente ordenada cronológicamente
            const pendingTasks = [...tasks]
                .sort((a, b) => a.time.localeCompare(b.time))
                .filter(t => !t.completed);

            if (pendingTasks.length > 0) {
                const next = pendingTasks[0];
                focusTitle.innerHTML = `<span class="font-mono font-semibold text-zinc-200">[${next.time}]</span> ${next.title}`;
            } else {
                focusTitle.innerText = "¡Enhorabuena! Has completado toda tu agenda";
            }
        }

        // RENDER DE TODA LA LÍNEA DE TIEMPO VERTICAL (Timeline)
        function renderTimeline() {
            const container = document.getElementById('timelineContainer');
            const emptyState = document.getElementById('timelineEmptyState');
            const verticalLine = document.getElementById('timelineVerticalLine');
            
            const selectedDay = daysArray[selectedDayIndex];
            const tasks = userRoutines[selectedDay.dateString] || [];

            if (tasks.length === 0) {
                container.innerHTML = '';
                emptyState.classList.remove('hidden');
                emptyState.classList.add('flex');
                verticalLine.classList.add('hidden');
                return;
            }

            emptyState.classList.add('hidden');
            emptyState.classList.remove('flex');
            verticalLine.classList.remove('hidden');

            // Ordenar por hora de forma cronológica estricta
            const sortedTasks = [...tasks].sort((a, b) => a.time.localeCompare(b.time));

            let html = '';
            sortedTasks.forEach((task, idx) => {
                // Definición sutil del color e ícono de la categoría de forma sobria
                let catColor = "bg-zinc-900 border-zinc-800 text-zinc-450";
                let catIcon = "fa-solid fa-briefcase";

                if (task.category === "Salud") {
                    catIcon = "fa-solid fa-heart-pulse";
                } else if (task.category === "Estudio") {
                    catIcon = "fa-solid fa-book-open";
                } else if (task.category === "Ocio") {
                    catIcon = "fa-solid fa-mug-hot";
                }

                const cardCompletedClass = task.completed 
                    ? "opacity-45 border-premium-border bg-black/40" 
                    : "border-premium-border/80 bg-zinc-950";

                const textCompletedClass = task.completed 
                    ? "line-through text-zinc-600 font-normal" 
                    : "text-zinc-200 font-medium";

                html += `
                    <div class="relative pl-12 pr-1 py-1 group">
                        
                        <!-- Nodo indicador de estado en la línea temporal -->
                        <div class="absolute left-4 top-1/2 -translate-y-1/2 w-4 h-4 rounded-full border flex items-center justify-center transition z-10 ${
                            task.completed 
                            ? 'bg-emerald-950/40 border-emerald-500 text-emerald-400' 
                            : 'bg-zinc-950 border-zinc-750 text-zinc-600 group-hover:border-zinc-500'
                        }">
                            <div class="w-1.5 h-1.5 rounded-full ${task.completed ? 'bg-emerald-400' : 'bg-transparent'}"></div>
                        </div>

                        <!-- Tarjeta de Actividad -->
                        <div class="border rounded-xl p-4 flex items-center justify-between gap-4 transition shadow-sm ${cardCompletedClass}">
                            
                            <div class="flex items-start space-x-3.5 min-w-0 flex-grow">
                                <!-- Hora fija elegante -->
                                <span class="text-xs font-mono font-medium text-zinc-400 bg-zinc-900 px-2 py-0.5 border border-premium-border rounded-md mt-0.5">
                                    ${task.time}
                                </span>
                                
                                <div class="space-y-1 min-w-0 flex-1">
                                    <h4 class="text-xs ${textCompletedClass} break-words leading-relaxed">${task.title}</h4>
                                    
                                    <div class="flex items-center space-x-2">
                                        <!-- Distintivo de categoría ultra-pequeño y sutil -->
                                        <span class="inline-flex items-center gap-1 text-[8px] uppercase tracking-widest text-zinc-500 font-semibold bg-zinc-900 px-1.5 py-0.5 rounded border border-premium-border">
                                            <i class="${catIcon} text-[7px] text-zinc-500"></i>
                                            <span>${task.category}</span>
                                        </span>
                                    </div>
                                </div>
                            </div>

                            <!-- Controles de acción: Check / Delete -->
                            <div class="flex items-center space-x-2 shrink-0">
                                <!-- Botón Check Sobrio con retroalimentación -->
                                <button onclick="toggleTaskCompletion('${task.id}')" 
                                    class="w-8 h-8 rounded-lg flex items-center justify-center border transition ${
                                        task.completed 
                                        ? 'bg-emerald-950/25 border-emerald-500/40 text-emerald-400 hover:bg-emerald-950/40' 
                                        : 'bg-zinc-900 border-zinc-800 text-zinc-500 hover:text-zinc-200 hover:border-zinc-600'
                                    }">
                                    <i class="fa-solid ${task.completed ? 'fa-check-double text-xs' : 'fa-check text-[10px]'}"></i>
                                </button>

                                <!-- Botón de Borrado sutil -->
                                <button onclick="deleteTask('${task.id}')" 
                                    class="w-8 h-8 rounded-lg bg-zinc-900/40 border border-transparent hover:border-red-900/40 text-zinc-600 hover:text-red-400 flex items-center justify-center transition">
                                    <i class="fa-regular fa-trash-can text-[10px]"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            });

            container.innerHTML = html;
        }

        // PROCESADOR DE INSTRUCCIONES ESCRITAS (Natural Language Parser en Español)
        function processNaturalLanguageRoutine() {
            const promptInput = document.getElementById('aiPromptInput');
            const text = promptInput.value.trim();

            if (!text) {
                showToast("Por favor escribe tus horarios y actividades primero.", "Instrucción vacía");
                return;
            }

            // Expresión regular inteligente para atrapar horas en formatos variados (ej: 07:30, 8:00, 14:00, 7pm, 10 am)
            const timePattern = /(?:\b|[^\d])((?:[01]?\d|2[0-3])[:.][0-5]\d(?:\s*(?:am|pm|AM|PM))?|\b(?:[01]?\d|2[0-3])\s*(?:am|pm|AM|PM)\b)/g;
            
            // Detección sutil del objetivo de día
            let targetDayStr = daysArray[selectedDayIndex].dateString; // por defecto el día activo en pantalla
            const textLower = text.toLowerCase();
            
            if (textLower.includes("mañana") || textLower.includes("manana")) {
                targetDayStr = daysArray[1].dateString;
                selectDay(1); // Mover el carrusel a mañana para ver el resultado
            } else if (textLower.includes("hoy")) {
                targetDayStr = daysArray[0].dateString;
                selectDay(0);
            }

            // Encontrar todos los horarios en el texto
            const matches = [];
            let match;
            while ((match = timePattern.exec(text)) !== null) {
                matches.push({
                    timeRaw: match[1],
                    index: match.index
                });
            }

            if (matches.length === 0) {
                showToast("No pudimos identificar horas válidas en tu descripción. Recuerda usar formatos como '08:30' o '15:00'.", "Análisis inconcluso");
                return;
            }

            const parsedTasks = [];

            for (let i = 0; i < matches.length; i++) {
                const current = matches[i];
                const next = matches[i + 1];

                // Extraer el texto de la tarea ubicado entre esta hora y la siguiente
                const startIdx = current.index + current.timeRaw.length;
                const endIdx = next ? next.index : text.length;
                
                let rawTitle = text.substring(startIdx, endIdx).trim();
                
                // Limpieza de caracteres de conexión frecuentes
                rawTitle = rawTitle.replace(/^[:.,\-y\s]+/, ''); // Limpiar conectores de inicio
                rawTitle = rawTitle.replace(/[,y\s\-]+$/, '');  // Limpiar conectores del final
                
                if (rawTitle.length === 0) {
                    rawTitle = "Actividad planificada";
                }

                // Normalización estética estricta de la hora para mantener formato HH:MM de 24 horas
                let cleanTime = normalizeTimeString(current.timeRaw);

                // Auto-categorización básica sobria
                let category = "Trabajo";
                const lowTitle = rawTitle.toLowerCase();
                if (lowTitle.includes("meditar") || lowTitle.includes("gimnasio") || lowTitle.includes("deporte") || lowTitle.includes("caminar") || lowTitle.includes("desayunar") || lowTitle.includes("dormir") || lowTitle.includes("almorzar") || lowTitle.includes("entrenar") || lowTitle.includes("comer") || lowTitle.includes("correr") || lowTitle.includes("salud")) {
                    category = "Salud";
                } else if (lowTitle.includes("estudiar") || lowTitle.includes("leer") || lowTitle.includes("curso") || lowTitle.includes("aprender") || lowTitle.includes("clase") || lowTitle.includes("universidad") || lowTitle.includes("investigar")) {
                    category = "Estudio";
                } else if (lowTitle.includes("descanso") || lowTitle.includes("ocio") || lowTitle.includes("película") || lowTitle.includes("jugar") || lowTitle.includes("relax") || lowTitle.includes("café") || lowTitle.includes("cafe")) {
                    category = "Ocio";
                }

                parsedTasks.push({
                    id: 'task_' + Math.random().toString(36).substr(2, 9),
                    time: cleanTime,
                    title: capitalizeFirstLetter(rawTitle),
                    category: category,
                    completed: false
                });
            }

            // Guardar e integrar en la base de datos
            if (!userRoutines[targetDayStr]) {
                userRoutines[targetDayStr] = [];
            }

            userRoutines[targetDayStr].push(...parsedTasks);
            saveToLocalStorage();
            
            // Actualizar vista
            renderTimeline();
            updateDailyProgress();
            updateDashboardFocusElement();

            // Limpiar área de texto
            promptInput.value = '';

            playSuccessChime();
            showToast(`Hemos mapeado y cargado exitosamente ${parsedTasks.length} actividades al cronograma.`, "Rutina creada");
        }

        // NORMALIZACIÓN DE HORARIO AL ESTÁNDAR HH:MM
        function normalizeTimeString(timeRaw) {
            let clean = timeRaw.toLowerCase().replace(/\s/g, '');
            let isPM = clean.includes('pm');
            let isAM = clean.includes('am');
            
            clean = clean.replace(/(am|pm)/, '');
            
            let hours = 0;
            let minutes = 0;

            if (clean.includes(':') || clean.includes('.')) {
                const parts = clean.split(/[:.]/);
                hours = parseInt(parts[0], 10);
                minutes = parseInt(parts[1], 10) || 0;
            } else {
                hours = parseInt(clean, 10);
            }

            if (isPM && hours < 12) hours += 12;
            if (isAM && hours === 12) hours = 0;

            const finalH = String(hours).padStart(2, '0');
            const finalM = String(minutes).padStart(2, '0');

            return `${finalH}:${finalM}`;
        }

        // AGREGAR TAREA DESDE EL FORMULARIO MANUAL
        function handleManualSubmit(e) {
            e.preventDefault();
            
            const titleInput = document.getElementById('manualTitle');
            const timeInput = document.getElementById('manualTime');
            const catSelect = document.getElementById('manualCategory');

            const selectedDay = daysArray[selectedDayIndex];
            
            const newTask = {
                id: 'task_' + Math.random().toString(36).substr(2, 9),
                time: timeInput.value,
                title: capitalizeFirstLetter(titleInput.value.trim()),
                category: catSelect.value,
                completed: false
            };

            if (!userRoutines[selectedDay.dateString]) {
                userRoutines[selectedDay.dateString] = [];
            }

            userRoutines[selectedDay.dateString].push(newTask);
            saveToLocalStorage();

            // Re-render
            renderTimeline();
            updateDailyProgress();
            updateDashboardFocusElement();

            // Limpiar campos de forma limpia
            titleInput.value = '';
            timeInput.value = '';

            playSuccessChime();
            showToast("Actividad añadida correctamente al cronograma diario.", "Actividad agregada");
        }

        // CAMBIO DE ESTADO COMPLETADO / PENDIENTE DE UNA TAREA
        function toggleTaskCompletion(taskId) {
            const selectedDay = daysArray[selectedDayIndex];
            const tasks = userRoutines[selectedDay.dateString] || [];
            
            const taskIndex = tasks.findIndex(t => t.id === taskId);
            if (taskIndex !== -1) {
                const isNowCompleted = !tasks[taskIndex].completed;
                tasks[taskIndex].completed = isNowCompleted;
                
                saveToLocalStorage();
                renderTimeline();
                
                const daySummary = updateDailyProgress();
                updateDashboardFocusElement();

                if (isNowCompleted) {
                    playSuccessChime();
                    // Verificar si completó el 100% de la agenda diaria
                    if (daySummary.total > 0 && daySummary.completed === daySummary.total) {
                        playCompleteDayFanfare();
                        showToast("¡Impresionante! Has cumplido el 100% de tus metas programadas para este día.", "Día completado");
                    }
                }
            }
        }

        // ELIMINACIÓN DE UNA ACTIVIDAD ESPECÍFICA
        function deleteTask(taskId) {
            const selectedDay = daysArray[selectedDayIndex];
            const tasks = userRoutines[selectedDay.dateString] || [];
            
            userRoutines[selectedDay.dateString] = tasks.filter(t => t.id !== taskId);
            
            saveToLocalStorage();
            renderTimeline();
            updateDailyProgress();
            updateDashboardFocusElement();
            showToast("La actividad seleccionada ha sido removida del cronograma.", "Actividad eliminada");
        }

        // LIMPIEZA TOTAL DE LA AGENDA DEL DÍA ACTIVO
        function clearTimeline() {
            const selectedDay = daysArray[selectedDayIndex];
            userRoutines[selectedDay.dateString] = [];
            
            saveToLocalStorage();
            renderTimeline();
            updateDailyProgress();
            updateDashboardFocusElement();
            showToast("Se han eliminado todas las actividades programadas para este día.", "Agenda despejada");
        }

        // ACTUALIZACIÓN DE MÉTRICAS GLOBALES DE PROGRESO DIARIO
        function updateDailyProgress() {
            const selectedDay = daysArray[selectedDayIndex];
            const tasks = userRoutines[selectedDay.dateString] || [];
            
            const total = tasks.length;
            const completed = tasks.filter(t => t.completed).length;
            
            let percentage = 0;
            if (total > 0) {
                percentage = Math.round((completed / total) * 100);
            }

            // Elementos DOM
            const percentageText = document.getElementById('progressPercentage');
            const completedText = document.getElementById('progressCompletedText');
            const progressCircle = document.getElementById('progressCircle');
            const trophy = document.getElementById('trophyIndicator');

            percentageText.innerText = `${percentage}%`;
            completedText.innerText = `${completed} de ${total} completadas`;

            // Animación del indicador circular de progreso (SVG stroke-dashoffset)
            // Circunferencia = 2 * PI * r = 2 * 3.1416 * 20 = 125.66
            const circumference = 125.66;
            const offset = circumference - (percentage / 100) * circumference;
            progressCircle.style.strokeDashoffset = offset;

            // Reemplazo visual de trofeo para 100% de éxito
            if (percentage === 100 && total > 0) {
                progressCircle.style.stroke = "#10b981"; // Esmeralda al finalizar
                trophy.classList.remove('hidden');
            } else {
                progressCircle.style.stroke = "#ffffff"; // Blanco estándar
                trophy.classList.add('hidden');
            }

            return { total, completed };
        }

        // MONITOR EN TIEMPO REAL - ENVÍO DE RECORDATORIOS ACTIVO (Toast de alerta cuando es la hora justa)
        const alertedTasks = new Set(); // Evitar duplicar alertas por minuto
        
        function checkActiveTaskReminders() {
            const today = new Date();
            const yyyy = today.getFullYear();
            const mm = String(today.getMonth() + 1).padStart(2, '0');
            const dd = String(today.getDate()).padStart(2, '0');
            
            const currentDateStr = `${yyyy}-${mm}-${dd}`;
            const currentHourMin = `${String(today.getHours()).padStart(2, '0')}:${String(today.getMinutes()).padStart(2, '0')}`;
            
            const todayTasks = userRoutines[currentDateStr] || [];
            
            todayTasks.forEach(task => {
                if (task.time === currentHourMin && !task.completed) {
                    const alertKey = `${task.id}_${currentHourMin}`;
                    if (!alertedTasks.has(alertKey)) {
                        alertedTasks.add(alertKey);
                        // Emitir campanilla sutil y lanzar Toast de alerta
                        playSuccessChime();
                        showToast(`Es hora de comenzar: "${task.title}"`, "Recordatorio activo", true);
                    }
                }
            });
        }

        // CREACIÓN Y MANEJO DE TOASTS FLOTANTES
        function showToast(message, title = "Notificación", isPersistent = false) {
            const container = document.getElementById('toastContainer');
            if (!container) return;

            const toast = document.createElement('div');
            toast.className = "pointer-events-auto bg-premium-black border border-premium-border p-4 rounded-xl shadow-premium flex items-start space-x-3 transition-all duration-300 transform translate-y-2 opacity-0 hover:border-zinc-700";
            
            toast.innerHTML = `
                <div class="w-5 h-5 rounded-full bg-zinc-900 border border-premium-border/80 flex items-center justify-center text-zinc-400 shrink-0 mt-0.5">
                    <i class="fa-regular fa-bell text-[9px]"></i>
                </div>
                <div class="flex-grow space-y-0.5">
                    <h5 class="text-[10px] font-sans font-bold text-white uppercase tracking-wider">${title}</h5>
                    <p class="text-[11px] text-zinc-450 leading-relaxed">${message}</p>
                </div>
                <button class="text-zinc-600 hover:text-zinc-400 shrink-0 ml-1" onclick="this.parentElement.remove()">
                    <i class="fa-solid fa-xmark text-xs"></i>
                </button>
            `;

            container.appendChild(toast);

            // Trigger animaciones de entrada fluidas
            setTimeout(() => {
                toast.classList.remove('translate-y-2', 'opacity-0');
            }, 10);

            // Remover automáticamente si no se define como persistente
            if (!isPersistent) {
                setTimeout(() => {
                    toast.classList.add('opacity-0', 'translate-y-1');
                    setTimeout(() => {
                        toast.remove();
                    }, 300);
                }, 4000);
            }
        }

        // RELOJ DINÁMICO EN EL ENCABEZADO
        function startLiveClock() {
            const display = document.getElementById('currentTimeDisplay');
            setInterval(() => {
                const now = new Date();
                display.innerText = now.toLocaleTimeString('es-ES', { hour12: false });
            }, 1000);
        }

        // AUXILIARES
        function capitalizeFirstLetter(string) {
            if (!string) return '';
            return string.charAt(0).toUpperCase() + string.slice(1);
        }

        // INICIALIZACIÓN GLOBAL DE LA APLICACIÓN AL CARGAR LA PÁGINA
        window.onload = function() {
            // Cargar o inicializar rutinas
            initializeMockRoutines();
            
            // Generar fechas del carrusel de 7 días
            generateDaysArray();
            renderDaysCarousel();
            
            // Seleccionar primer día (Hoy)
            selectDay(0);

            // Iniciar Reloj de la barra superior
            startLiveClock();

            // Activar sistema periódico de alertas de recordatorio (cada 15 segundos para optimizar recursos)
            setInterval(checkActiveTaskReminders, 15000);
        }
    </script>
</body>
</html>
