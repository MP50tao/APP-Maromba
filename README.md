<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plano Completo - 4 Treinos Animados</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* CSS Customizado e Animações dos Exercícios */
        @keyframes barbellPress {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-35px); }
        }
        @keyframes dumbbellFly {
            0%, 100% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(-25deg) scale(0.9); }
        }
        @keyframes dipMove {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(25px); }
        }
        @keyframes pulldownMove {
            0%, 100% { transform: translateY(-30px); }
            50% { transform: translateY(0px); }
        }
        @keyframes rowMove {
            0%, 100% { transform: translateX(0px) translateY(0px); }
            50% { transform: translateX(-20px) translateY(-10px); }
        }
        @keyframes squatMove {
            0%, 100% { transform: translateY(0px) scaleY(1); }
            50% { transform: translateY(30px) scaleY(0.85); }
        }
        @keyframes crunchMove {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(20deg); }
        }
        @keyframes legRaiseMove {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-70deg); }
        }
        @keyframes curlMove {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(-110deg); }
        }

        .anim-active .anim-press { animation: barbellPress 1.5s infinite ease-in-out; }
        .anim-active .anim-fly { animation: dumbbellFly 1.8s infinite ease-in-out; }
        .anim-active .anim-dip { animation: dipMove 1.6s infinite ease-in-out; }
        .anim-active .anim-pulldown { animation: pulldownMove 1.6s infinite ease-in-out; }
        .anim-active .anim-row { animation: rowMove 1.5s infinite ease-in-out; }
        .anim-active .anim-squat { animation: squatMove 1.8s infinite ease-in-out; transform-origin: bottom center; }
        .anim-active .anim-crunch { animation: crunchMove 1.4s infinite ease-in-out; transform-origin: bottom right; }
        .anim-active .anim-legraise { animation: legRaiseMove 1.6s infinite ease-in-out; transform-origin: top left; }
        .anim-active .anim-curl { animation: curlMove 1.4s infinite ease-in-out; transform-origin: bottom left; }

        /* Estilização dos Scrollbars */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #1f2937;
        }
        ::-webkit-scrollbar-thumb {
            background: #4b5563;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #6b7280;
        }
    </style>
</head>
<body class="bg-slate-950 text-white min-h-screen font-sans pb-12">

    <!-- Cabeçalho -->
    <header class="bg-gradient-to-r from-blue-900 via-slate-900 to-purple-900 border-b border-slate-800 p-6 text-center shadow-xl sticky top-0 z-50 backdrop-blur-md bg-opacity-90">
        <h1 class="text-3xl md:text-5xl font-black tracking-wider uppercase text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 via-orange-300 to-yellow-500">
            PLANO COMPLETO — 4 TREINOS
        </h1>
        <p class="text-slate-300 text-sm md:text-base font-semibold mt-1 tracking-widest uppercase">
            Guia Interativo com Exercícios Animados
        </p>
    </header>

    <!-- Navegação de Treinos -->
    <div class="max-w-7xl mx-auto px-4 mt-6">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mb-8">
            <button onclick="switchTab('treinoA')" id="btn-treinoA" class="tab-btn p-4 rounded-xl font-bold text-center transition-all shadow-lg border border-blue-500/30 bg-blue-900/40 text-blue-300 hover:bg-blue-800/60 flex flex-col items-center gap-1">
                <span class="text-xs uppercase tracking-wider opacity-75">Treino A</span>
                <span class="text-base md:text-lg font-black">PEITO + TRÍCEPS</span>
            </button>
            <button onclick="switchTab('treinoB')" id="btn-treinoB" class="tab-btn p-4 rounded-xl font-bold text-center transition-all shadow-lg border border-emerald-500/30 bg-emerald-900/20 text-emerald-300 hover:bg-emerald-800/60 flex flex-col items-center gap-1">
                <span class="text-xs uppercase tracking-wider opacity-75">Treino B</span>
                <span class="text-base md:text-lg font-black">COSTAS + BÍCEPS</span>
            </button>
            <button onclick="switchTab('treinoC')" id="btn-treinoC" class="tab-btn p-4 rounded-xl font-bold text-center transition-all shadow-lg border border-orange-500/30 bg-orange-900/20 text-orange-300 hover:bg-orange-800/60 flex flex-col items-center gap-1">
                <span class="text-xs uppercase tracking-wider opacity-75">Treino C</span>
                <span class="text-base md:text-lg font-black">OMBROS + ABDÔMEN</span>
            </button>
            <button onclick="switchTab('treinoD')" id="btn-treinoD" class="tab-btn p-4 rounded-xl font-bold text-center transition-all shadow-lg border border-purple-500/30 bg-purple-900/20 text-purple-300 hover:bg-purple-800/60 flex flex-col items-center gap-1">
                <span class="text-xs uppercase tracking-wider opacity-75">Treino D</span>
                <span class="text-base md:text-lg font-black">INFERIORES COMPLETO</span>
            </button>
        </div>

        <!-- Seções dos Treinos -->
        <main id="workouts-container">
            <!-- Treino A -->
            <section id="treinoA" class="workout-section space-y-4">
                <div class="flex justify-between items-center bg-blue-950/80 border border-blue-600/40 p-4 rounded-xl mb-4">
                    <h2 class="text-2xl font-black text-blue-400 flex items-center gap-3">
                        <span class="bg-blue-600 text-white px-3 py-1 rounded-lg text-lg">A</span> PEITO + TRÍCEPS
                    </h2>
                    <span class="text-slate-400 text-sm hidden sm:inline">7 Exercícios • Hipertrofia</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4" id="cards-treinoA"></div>
            </section>

            <!-- Treino B -->
            <section id="treinoB" class="workout-section hidden space-y-4">
                <div class="flex justify-between items-center bg-emerald-950/80 border border-emerald-600/40 p-4 rounded-xl mb-4">
                    <h2 class="text-2xl font-black text-emerald-400 flex items-center gap-3">
                        <span class="bg-emerald-600 text-white px-3 py-1 rounded-lg text-lg">B</span> COSTAS + BÍCEPS
                    </h2>
                    <span class="text-slate-400 text-sm hidden sm:inline">7 Exercícios • Hipertrofia</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4" id="cards-treinoB"></div>
            </section>

            <!-- Treino C -->
            <section id="treinoC" class="workout-section hidden space-y-4">
                <div class="flex justify-between items-center bg-orange-950/80 border border-orange-600/40 p-4 rounded-xl mb-4">
                    <h2 class="text-2xl font-black text-orange-400 flex items-center gap-3">
                        <span class="bg-orange-600 text-white px-3 py-1 rounded-lg text-lg">C</span> OMBROS + ABDÔMEN
                    </h2>
                    <span class="text-slate-400 text-sm hidden sm:inline">7 Exercícios • Definição & Core</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4" id="cards-treinoC"></div>
            </section>

            <!-- Treino D -->
            <section id="treinoD" class="workout-section hidden space-y-4">
                <div class="flex justify-between items-center bg-purple-950/80 border border-purple-600/40 p-4 rounded-xl mb-4">
                    <h2 class="text-2xl font-black text-purple-400 flex items-center gap-3">
                        <span class="bg-purple-600 text-white px-3 py-1 rounded-lg text-lg">D</span> INFERIORES COMPLETO
                    </h2>
                    <span class="text-slate-400 text-sm hidden sm:inline">7 Exercícios • Força & Base</span>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4" id="cards-treinoD"></div>
            </section>
        </main>
    </div>

    <!-- Modal de Detalhes do Exercício -->
    <div id="exercise-modal" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
        <div class="bg-slate-900 border border-slate-700 w-full max-w-xl rounded-2xl p-6 relative shadow-2xl space-y-4">
            <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white bg-slate-800 p-2 rounded-full">
                ✕
            </button>
            <div id="modal-content"></div>
        </div>
    </div>

    <script>
        // Dados dos treinos idênticos ao plano da imagem
        const workoutsData = {
            treinoA: [
                { id: "a1", num: "01", name: "SUPINO RETO COM BARRA", sets: "3 x 8–10", type: "press", color: "blue", desc: "Mantenha as escápulas retadas e pés firmes no chão." },
                { id: "a2", num: "02", name: "SUPINO INCLINADO COM HALTERES", sets: "3 x 8–10", type: "press", color: "blue", desc: "Ajuste o banco entre 30° e 45° de inclinação." },
                { id: "a3", num: "03", name: "CRUCIFIXO NO PECK DECK", sets: "3 x 10–12", type: "fly", color: "blue", desc: "Mantenha cotovelos levemente flexionados ao fechar." },
                { id: "a4", num: "04", name: "MERGULHO PARALELO", sets: "3 x 10–12", type: "dip", color: "blue", desc: "Incline levemente o tronco à frente para focar no peito." },
                { id: "a5", num: "05", name: "TRÍCEPS TESTA COM BARRA", sets: "3 x 10–12", type: "press", color: "blue", desc: "Fixe os cotovelos e desça a barra em direção à testa." },
                { id: "a6", num: "06", name: "TRÍCEPS CORDA NA POLIA", sets: "3 x 12–15", type: "pulldown", color: "blue", desc: "Afaste as cordas no final do movimento de extensão." },
                { id: "a7", num: "07", name: "TRÍCEPS FRANCÊS COM HALTER", sets: "3 x 12–15", type: "press", color: "blue", desc: "Mantenha cotovelos apontados para cima." }
            ],
            treinoB: [
                { id: "b1", num: "01", name: "PULLOVER NA POLIA", sets: "3 x 10–12", type: "pulldown", color: "emerald", desc: "Sinta a grande dorsal alongar totalmente no topo." },
                { id: "b2", num: "02", name: "PUXADA FRENTE NA POLIA ALTA", sets: "3 x 10–12", type: "pulldown", color: "emerald", desc: "Puxe a barra em direção ao peitoral superior." },
                { id: "b3", num: "03", name: "REMADA CURVADA COM BARRA", sets: "3 x 8–10", type: "row", color: "emerald", desc: "Coluna neutra e joelhos levemente flexionados." },
                { id: "b4", num: "04", name: "REMADA SENTADA NA POLIA", sets: "3 x 10–12", type: "row", color: "emerald", desc: "Puxe o triângulo até o abdômen contraindo as costas." },
                { id: "b5", num: "05", name: "FACE PULL NA POLIA", sets: "3 x 12–15", type: "pulldown", color: "emerald", desc: "Foco nos deltoides posteriores e manguito rotador." },
                { id: "b6", num: "06", name: "ROSCA DIRETA COM BARRA", sets: "3 x 8–10", type: "curl", color: "emerald", desc: "Evite balançar o tronco durante a execução." },
                { id: "b7", num: "07", name: "ROSCA MARTELO COM HALTERES", sets: "3 x 10–12", type: "curl", color: "emerald", desc: "Pegada neutra para trabalhar o braquiorradial." }
            ],
            treinoC: [
                { id: "c1", num: "01", name: "DESENVOLVIMENTO MILITAR COM BARRA", sets: "3 x 8–10", type: "press", color: "orange", desc: "Empurre a barra verticalmente acima da cabeça." },
                { id: "c2", num: "02", name: "ELEVAÇÃO LATERAL COM HALTERES", sets: "3 x 10–12", type: "fly", color: "orange", desc: "Eleve os braços até a linha dos ombros." },
                { id: "c3", num: "03", name: "ELEVAÇÃO FRONTAL COM HALTERES", sets: "3 x 10–12", type: "fly", color: "orange", desc: "Eleve o peso à frente até a altura do peito." },
                { id: "c4", num: "04", name: "VOADOR INVERSO NO PECK DECK", sets: "3 x 12–15", type: "fly", color: "orange", desc: "Foco total na parte posterior dos ombros." },
                { id: "c5", num: "05", name: "CRUNCH ABDOMINAL", sets: "3 x 15–20", type: "crunch", color: "orange", desc: "Contraia forte o abdômen sem forçar o pescoço." },
                { id: "c6", num: "06", name: "ELEVAÇÃO DE PERNAS NA BARRA", sets: "3 x 12–15", type: "legraise", color: "orange", desc: "Eleve os joelhos ou pernas até 90°." },
                { id: "c7", num: "07", name: "PRANCHA ISOMÉTRICA", sets: "3 x 30–60s", type: "hold", color: "orange", desc: "Mantenha o corpo em linha reta e o core ativado." }
            ],
            treinoD: [
                { id: "d1", num: "01", name: "AGACHAMENTO NO SMITH", sets: "3 x 10", type: "squat", color: "purple", desc: "Agache mantendo a postura firme dos joelhos." },
                { id: "d2", num: "02", name: "LEG PRESS", sets: "3 x 12", type: "squat", color: "purple", desc: "Empurre a plataforma sem travar totalmente os joelhos." },
                { id: "d3", num: "03", name: "CADEIRA FLEXORA", sets: "3 x 10–12", type: "curl", color: "purple", desc: "Flexione as pernas focando nos isquiotibiais." },
                { id: "d4", num: "04", name: "STIFF", sets: "3 x 10", type: "squat", color: "purple", desc: "Desça a barra mantendo a coluna totalmente ereta." },
                { id: "d5", num: "05", name: "CADEIRA EXTENSORA", sets: "3 x 12–15", type: "hold", color: "purple", desc: "Extensão de joelhos com foco total nos quadríceps." },
                { id: "d6", num: "06", name: "ELEVAÇÃO PÉLVICA", sets: "3 x 10–12", type: "crunch", color: "purple", desc: "Contração máxima dos glúteos no topo do movimento." },
                { id: "d7", num: "07", name: "PANTURRILHA SENTADA", sets: "3 x 15–20", type: "press", color: "purple", desc: "Amplitude máxima subindo e descendo os calcanhares." }
            ]
        };

        // Renderizar SVG dinâmico com Animações de Exercício
        function generateExerciseSVG(type, color = "blue", isPlaying = true) {
            const animClass = isPlaying ? "anim-active" : "";
            
            const colorClasses = {
                blue: { stroke: "#3b82f6", fill: "#60a5fa", bg: "#1e3a8a" },
                emerald: { stroke: "#10b981", fill: "#34d399", bg: "#064e3b" },
                orange: { stroke: "#f97316", fill: "#fb923c", bg: "#7c2d12" },
                purple: { stroke: "#a855f7", fill: "#c084fc", bg: "#581c87" }
            };
            const c = colorClasses[color] || colorClasses.blue;

            let bodyContent = "";

            switch(type) {
                case "press":
                    bodyContent = `
                        <!-- Banco -->
                        <rect x="20" y="110" width="160" height="12" rx="4" fill="#334155"/>
                        <rect x="50" y="122" width="10" height="30" fill="#1e293b"/>
                        <rect x="140" y="122" width="10" height="30" fill="#1e293b"/>
                        <!-- Boneco Supino -->
                        <g class="anim-press">
                            <!-- Tronco -->
                            <path d="M 60,105 L 140,105" stroke="${c.stroke}" stroke-width="12" stroke-linecap="round"/>
                            <!-- Cabeça -->
                            <circle cx="50" cy="105" r="10" fill="${c.fill}"/>
                            <!-- Barra e Peso -->
                            <g>
                                <line x1="90" y1="40" x2="90" y2="100" stroke="#94a3b8" stroke-width="4"/>
                                <rect x="80" y="30" width="20" height="75" fill="#f59e0b" rx="2"/>
                                <circle cx="90" cy="65" r="12" fill="${c.fill}"/>
                            </g>
                        </g>
                    `;
                    break;
                case "fly":
                    bodyContent = `
                        <!-- Aparelho/Halteres -->
                        <circle cx="100" cy="70" r="14" fill="${c.fill}"/>
                        <path d="M 100,84 L 100,120" stroke="${c.stroke}" stroke-width="10" stroke-linecap="round"/>
                        <g class="anim-fly">
                            <!-- Braço Esquerdo -->
                            <line x1="100" y1="90" x2="50" y2="70" stroke="${c.stroke}" stroke-width="8" stroke-linecap="round"/>
                            <circle cx="45" cy="68" r="8" fill="#e2e8f0"/>
                            <!-- Braço Direito -->
                            <line x1="100" y1="90" x2="150" y2="70" stroke="${c.stroke}" stroke-width="8" stroke-linecap="round"/>
                            <circle cx="155" cy="68" r="8" fill="#e2e8f0"/>
                        </g>
                    `;
                    break;
                case "dip":
                    bodyContent = `
                        <!-- Barras Paralelas -->
                        <line x1="60" y1="80" x2="60" y2="150" stroke="#64748b" stroke-width="8"/>
                        <line x1="140" y1="80" x2="140" y2="150" stroke="#64748b" stroke-width="8"/>
                        <g class="anim-dip">
                            <circle cx="100" cy="40" r="12" fill="${c.fill}"/>
                            <path d="M 100,52 L 100,90" stroke="${c.stroke}" stroke-width="10"/>
                            <!-- Braços na Barra -->
                            <polyline points="100,60 60,70 60,80" fill="none" stroke="${c.stroke}" stroke-width="6"/>
                            <polyline points="100,60 140,70 140,80" fill="none" stroke="${c.stroke}" stroke-width="6"/>
                            <!-- Pernas -->
                            <polyline points="100,90 110,120 105,140" fill="none" stroke="${c.stroke}" stroke-width="8"/>
                        </g>
                    `;
                    break;
                case "pulldown":
                    bodyContent = `
                        <!-- Cabo e Polia -->
                        <line x1="100" y1="10" x2="100" y2="60" stroke="#94a3b8" stroke-width="3"/>
                        <rect x="60" y="10" width="80" height="6" fill="#475569"/>
                        <g class="anim-pulldown">
                            <line x1="60" y1="50" x2="140" y2="50" stroke="#e2e8f0" stroke-width="6" stroke-linecap="round"/>
                            <!-- Braços puxando -->
                            <path d="M 60,50 L 80,80 L 100,90" fill="none" stroke="${c.stroke}" stroke-width="6"/>
                            <path d="M 140,50 L 120,80 L 100,90" fill="none" stroke="${c.stroke}" stroke-width="6"/>
                        </g>
                        <!-- Corpo -->
                        <circle cx="100" cy="75" r="12" fill="${c.fill}"/>
                        <path d="M 100,87 L 100,130" stroke="${c.stroke}" stroke-width="12"/>
                    `;
                    break;
                case "row":
                    bodyContent = `
                        <!-- Remada Curvada/Sentada -->
                        <g class="anim-row">
                            <circle cx="60" cy="50" r="12" fill="${c.fill}"/>
                            <path d="M 60,62 L 90,95 L 130,95" fill="none" stroke="${c.stroke}" stroke-width="10" stroke-linecap="round"/>
                            <!-- Barra/Peso puxado -->
                            <circle cx="100" cy="90" r="10" fill="#f59e0b"/>
                            <line x1="100" y1="70" x2="100" y2="110" stroke="#cbd5e1" stroke-width="5"/>
                        </g>
                        <!-- Pernas fixas -->
                        <polyline points="130,95 140,125 150,145" fill="none" stroke="${c.stroke}" stroke-width="8"/>
                    `;
                    break;
                case "squat":
                    bodyContent = `
                        <g class="anim-squat">
                            <!-- Cabeça -->
                            <circle cx="100" cy="35" r="12" fill="${c.fill}"/>
                            <!-- Tronco -->
                            <line x1="100" y1="47" x2="100" y2="90" stroke="${c.stroke}" stroke-width="12" stroke-linecap="round"/>
                            <!-- Barra com Pesos -->
                            <line x1="50" y1="45" x2="150" y2="45" stroke="#94a3b8" stroke-width="6"/>
                            <rect x="40" y="30" width="12" height="30" fill="#f59e0b"/>
                            <rect x="148" y="30" width="12" height="30" fill="#f59e0b"/>
                            <!-- Pernas/Agachamento -->
                            <polyline points="100,90 75,115 80,145" fill="none" stroke="${c.stroke}" stroke-width="8" stroke-linecap="round"/>
                            <polyline points="100,90 125,115 120,145" fill="none" stroke="${c.stroke}" stroke-width="8" stroke-linecap="round"/>
                        </g>
                    `;
                    break;
                case "crunch":
                    bodyContent = `
                        <rect x="30" y="125" width="140" height="8" fill="#334155" rx="3"/>
                        <!-- Pernas dobradas -->
                        <polyline points="130,125 150,95 135,70" fill="none" stroke="${c.stroke}" stroke-width="8"/>
                        <!-- Tronco fazendo crunch -->
                        <g class="anim-crunch">
                            <circle cx="50" cy="90" r="12" fill="${c.fill}"/>
                            <line x1="60" y1="100" x2="110" y2="125" stroke="${c.stroke}" stroke-width="12" stroke-linecap="round"/>
                        </g>
                    `;
                    break;
                case "legraise":
                    bodyContent = `
                        <!-- Barra de Sustentação -->
                        <line x1="30" y1="30" x2="100" y2="30" stroke="#64748b" stroke-width="8"/>
                        <!-- Tronco suspenso -->
                        <circle cx="70" cy="50" r="10" fill="${c.fill}"/>
                        <line x1="70" y1="60" x2="70" y2="100" stroke="${c.stroke}" stroke-width="10"/>
                        <!-- Pernas elevando -->
                        <g class="anim-legraise">
                            <line x1="70" y1="100" x2="70" y2="145" stroke="${c.stroke}" stroke-width="8" stroke-linecap="round"/>
                        </g>
                    `;
                    break;
                case "curl":
                    bodyContent = `
                        <!-- Corpo fixo -->
                        <circle cx="80" cy="45" r="12" fill="${c.fill}"/>
                        <line x1="80" y1="57" x2="80" y2="110" stroke="${c.stroke}" stroke-width="12"/>
                        <line x1="80" y1="110" x2="70" y2="145" stroke="${c.stroke}" stroke-width="8"/>
                        <!-- Braço fazendo rosca -->
                        <g class="anim-curl" style="transform-origin: 80px 70px;">
                            <line x1="80" y1="70" x2="80" y2="110" stroke="${c.stroke}" stroke-width="7"/>
                            <circle cx="80" cy="115" r="10" fill="#f59e0b"/>
                        </g>
                    `;
                    break;
                default: // Hold / Prancha
                    bodyContent = `
                        <rect x="20" y="130" width="160" height="6" fill="#334155"/>
                        <!-- Prancha -->
                        <g class="anim-press">
                            <circle cx="45" cy="105" r="10" fill="${c.fill}"/>
                            <path d="M 50,110 L 130,110" stroke="${c.stroke}" stroke-width="10" stroke-linecap="round"/>
                            <!-- Antebraço -->
                            <polyline points="55,110 55,128 70,128" fill="none" stroke="${c.stroke}" stroke-width="5"/>
                            <!-- Pés -->
                            <line x1="130" y1="110" x2="140" y2="128" stroke="${c.stroke}" stroke-width="6"/>
                        </g>
                    `;
            }

            return `
                <svg viewBox="0 0 200 160" class="w-full h-36 rounded-lg bg-slate-900 border border-slate-800 p-2 ${animClass}">
                    ${bodyContent}
                </svg>
            `;
        }

        // Renderizar Lista de Cards de Exercício
        function renderWorkouts() {
            Object.keys(workoutsData).forEach(workoutKey => {
                const container = document.getElementById(`cards-${workoutKey}`);
                if (!container) return;

                const exercises = workoutsData[workoutKey];
                container.innerHTML = exercises.map(ex => {
                    const savedWeight = localStorage.getItem(`weight_${ex.id}`) || '';
                    const savedNotes = localStorage.getItem(`notes_${ex.id}`) || '';

                    return `
                        <div class="bg-slate-900 border border-slate-800 hover:border-slate-700 rounded-xl p-4 shadow-lg flex flex-col justify-between transition-all">
                            <div>
                                <!-- Topo do Card -->
                                <div class="flex items-center justify-between mb-2">
                                    <span class="bg-slate-800 text-slate-300 font-bold px-2.5 py-1 rounded-md text-xs">
                                        EXERCÍCIO ${ex.num}
                                    </span>
                                    <span class="text-xs font-semibold px-2 py-1 rounded bg-slate-800 text-yellow-400 border border-yellow-500/20">
                                        📊 ${ex.sets}
                                    </span>
                                </div>

                                <!-- Título -->
                                <h3 class="font-extrabold text-slate-100 text-base leading-snug mb-3">
                                    ${ex.name}
                                </h3>

                                <!-- Ilustração Animada -->
                                <div class="relative group cursor-pointer" onclick="openModal('${workoutKey}', '${ex.id}')">
                                    ${generateExerciseSVG(ex.type, ex.color, true)}
                                    <div class="absolute inset-0 bg-black/40 opacity-0 group-hover:opacity-100 transition-opacity rounded-lg flex items-center justify-center text-xs font-bold text-white bg-opacity-30">
                                        🔍 Clique para Detalhes
                                    </div>
                                </div>
                            </div>

                            <!-- Campos de Entrada (Carga e Anotações) -->
                            <div class="mt-4 pt-3 border-t border-slate-800 space-y-2">
                                <div class="flex items-center gap-2">
                                    <span class="text-xs text-slate-400 font-medium">⚖️ Carga:</span>
                                    <input type="text" 
                                           placeholder="Ex: 20 kg" 
                                           value="${savedWeight}"
                                           onchange="saveData('weight_${ex.id}', this.value)"
                                           class="bg-slate-800 text-slate-200 text-xs px-2 py-1 rounded border border-slate-700 w-full focus:outline-none focus:border-blue-500">
                                </div>
                                <div class="flex items-center gap-2">
                                    <span class="text-xs text-slate-400 font-medium">📝 Notas:</span>
                                    <input type="text" 
                                           placeholder="Obs. do treino..." 
                                           value="${savedNotes}"
                                           onchange="saveData('notes_${ex.id}', this.value)"
                                           class="bg-slate-800 text-slate-200 text-xs px-2 py-1 rounded border border-slate-700 w-full focus:outline-none focus:border-blue-500">
                                </div>
                            </div>
                        </div>
                    `;
                }).join('');
            });
        }

        // Troca de Abas de Treino
        function switchTab(tabId) {
            document.querySelectorAll('.workout-section').forEach(sec => sec.classList.add('hidden'));
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('ring-2', 'ring-yellow-400', 'scale-105');
                btn.classList.add('opacity-70');
            });

            const activeSection = document.getElementById(tabId);
            const activeBtn = document.getElementById(`btn-${tabId}`);

            if (activeSection && activeBtn) {
                activeSection.classList.remove('hidden');
                activeBtn.classList.remove('opacity-70');
                activeBtn.classList.add('ring-2', 'ring-yellow-400', 'scale-105');
            }
        }

        // Salvar Cargas / Obs no LocalStorage
        function saveData(key, val) {
            localStorage.setItem(key, val);
        }

        // Abrir Modal
        function openModal(workoutKey, exId) {
            const exercise = workoutsData[workoutKey].find(e => e.id === exId);
            if (!exercise) return;

            const modalContent = document.getElementById('modal-content');
            modalContent.innerHTML = `
                <div class="space-y-4">
                    <div class="flex items-center gap-2">
                        <span class="bg-yellow-500 text-slate-950 text-xs font-black px-2 py-1 rounded">EXERCÍCIO ${exercise.num}</span>
                        <h3 class="text-xl font-black text-white">${exercise.name}</h3>
                    </div>

                    <div class="p-2 bg-slate-950 rounded-xl border border-slate-800">
                        ${generateExerciseSVG(exercise.type, exercise.color, true)}
                    </div>

                    <div class="bg-slate-800/60 p-4 rounded-xl space-y-2 border border-slate-700/50">
                        <div class="flex justify-between items-center">
                            <span class="text-sm text-slate-400 font-semibold">Séries x Repetições:</span>
                            <span class="text-sm font-bold text-yellow-400">${exercise.sets}</span>
                        </div>
                        <p class="text-sm text-slate-300 leading-relaxed pt-2 border-t border-slate-700/50">
                            💡 <strong class="text-slate-100">Dica de Execução:</strong> ${exercise.desc}
                        </p>
                    </div>

                    <button onclick="closeModal()" class="w-full bg-blue-600 hover:bg-blue-500 text-white font-bold py-2.5 rounded-xl transition-all">
                        Entendido / Voltar
                    </button>
                </div>
            `;

            document.getElementById('exercise-modal').classList.remove('hidden');
        }

        // Fechar Modal
        function closeModal() {
            document.getElementById('exercise-modal').classList.add('hidden');
        }

        // Inicialização
        window.onload = function() {
            renderWorkouts();
            switchTab('treinoA');
        };
    </script>
</body>
</html>

