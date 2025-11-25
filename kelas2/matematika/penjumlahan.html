import React, { useState, useEffect, useCallback, useRef } from 'react';
import { Trophy, Clock, RefreshCw, Play, Users, User, AlertCircle } from 'lucide-react';

// --- STYLES & CONFIG ---
const COLORS = {
  p1: 'bg-blue-500',
  p1Hover: 'hover:bg-blue-600',
  p1Light: 'bg-blue-100',
  p1Text: 'text-blue-600',
  p2: 'bg-red-500',
  p2Hover: 'hover:bg-red-600',
  p2Light: 'bg-red-100',
  p2Text: 'text-red-600',
  bg: 'bg-yellow-50',
  rope: 'bg-amber-700'
};

// --- DATA GENERATOR ---
const generateQuestionBank = () => {
  const bank = [];
  // Generate all pairs summing to <= 20
  for (let i = 0; i <= 20; i++) {
    for (let j = 0; j <= 20; j++) {
      if (i + j <= 20 && i + j > 0) {
        bank.push({ a: i, b: j, ans: i + j });
      }
    }
  }
  // Shuffle and pick 50 unique conceptual questions (though we only need 10 per game)
  return bank.sort(() => Math.random() - 0.5).slice(0, 50);
};

// --- COMPONENTS ---

const Keypad = ({ onInput, onSubmit, onClear, currentValue, disabled, colorTheme, label }) => {
  const keys = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];

  return (
    <div className={`p-4 rounded-xl shadow-lg ${colorTheme.bg} border-4 ${colorTheme.border} flex flex-col gap-2 w-full max-w-sm`}>
      <h3 className={`text-center font-bold uppercase ${colorTheme.text} mb-2`}>{label}</h3>
      
      {/* Screen */}
      <div className="bg-white h-16 rounded-lg border-2 border-gray-300 flex items-center justify-center mb-2 overflow-hidden relative">
        <span className="text-3xl font-mono font-bold tracking-widest text-gray-800">
          {currentValue === '' ? <span className="text-gray-300 opacity-50">?</span> : currentValue}
        </span>
      </div>

      {/* Grid */}
      <div className="grid grid-cols-3 gap-2">
        {keys.map((k) => (
          <button
            key={k}
            onClick={() => !disabled && onInput(k)}
            disabled={disabled}
            className={`
              h-12 rounded-lg font-bold text-xl transition-all active:scale-95 shadow-sm
              ${disabled ? 'bg-gray-200 text-gray-400' : 'bg-white text-gray-700 hover:bg-gray-50'}
              ${k === 0 ? 'col-span-3' : ''}
            `}
          >
            {k}
          </button>
        ))}
      </div>

      {/* Actions */}
      <div className="grid grid-cols-2 gap-2 mt-1">
        <button
          onClick={onClear}
          disabled={disabled}
          className="h-12 bg-gray-200 text-gray-600 rounded-lg font-bold hover:bg-gray-300 active:scale-95"
        >
          HAPUS
        </button>
        <button
          onClick={onSubmit}
          disabled={disabled}
          className={`h-12 ${colorTheme.main} text-white rounded-lg font-bold ${disabled ? 'opacity-50' : colorTheme.hover} active:scale-95 shadow-md`}
        >
          JAWAB!
        </button>
      </div>
    </div>
  );
};

const RopeArena = ({ position, winner }) => {
  // position range: -5 (Left Wins) to 5 (Right Wins). 0 is center.
  // We map -5..5 to a percentage for CSS transform.
  
  // Visual limit calculation
  const clampedPos = Math.max(-5, Math.min(5, position));
  const offset = clampedPos * 10; // 10% movement per point

  return (
    <div className="relative w-full h-32 flex items-center justify-center overflow-hidden my-4 bg-green-100 border-y-4 border-green-300 rounded-lg">
      
      {/* Background Decor (Center Line) */}
      <div className="absolute h-full w-2 bg-white opacity-50 z-0"></div>
      
      {/* Mud Pits */}
      <div className="absolute left-0 h-full w-16 bg-amber-900/20 border-r-4 border-amber-900/30 z-0 flex items-center justify-center text-xs font-bold text-amber-800 opacity-50">LUMPUR</div>
      <div className="absolute right-0 h-full w-16 bg-amber-900/20 border-l-4 border-amber-900/30 z-0 flex items-center justify-center text-xs font-bold text-amber-800 opacity-50">LUMPUR</div>

      {/* The Moving Group */}
      <div 
        className="flex items-center transition-transform duration-500 ease-in-out z-10 relative"
        style={{ transform: `translateX(${offset}%)` }}
      >
        {/* Left Team (Cat) */}
        <div className={`flex flex-col items-center mr-1 transition-transform ${winner === 'p1' ? '-rotate-12 scale-110' : ''}`}>
           <div className={`w-16 h-16 rounded-full border-4 border-blue-500 bg-blue-100 flex items-center justify-center text-4xl shadow-lg relative ${position < 0 ? 'animate-bounce' : ''}`}>
             🐱
             {/* Sweat drops if losing */}
             {position > 2 && <span className="absolute -top-2 -right-2 text-sm">💦</span>}
           </div>
           <span className="bg-blue-600 text-white text-xs px-2 py-0.5 rounded-full mt-1 font-bold">TIM KIRI</span>
        </div>

        {/* Rope */}
        <div className="h-4 w-48 bg-amber-700 mx-2 relative flex items-center justify-center shadow-inner rounded-full"
             style={{ backgroundImage: 'repeating-linear-gradient(45deg, transparent, transparent 10px, rgba(0,0,0,0.2) 10px, rgba(0,0,0,0.2) 20px)' }}>
          {/* Flag */}
          <div className="absolute w-1 h-8 bg-red-600 top-[-10px] left-1/2 -translate-x-1/2 shadow-md"></div>
          <div className="absolute w-4 h-3 bg-red-600 top-[-10px] left-1/2"></div>
        </div>

        {/* Right Team (Dog) */}
        <div className={`flex flex-col items-center ml-1 transition-transform ${winner === 'p2' ? 'rotate-12 scale-110' : ''}`}>
           <div className={`w-16 h-16 rounded-full border-4 border-red-500 bg-red-100 flex items-center justify-center text-4xl shadow-lg relative ${position > 0 ? 'animate-bounce' : ''}`}>
             🐶
             {/* Sweat drops if losing */}
             {position < -2 && <span className="absolute -top-2 -left-2 text-sm">💦</span>}
           </div>
           <span className="bg-red-600 text-white text-xs px-2 py-0.5 rounded-full mt-1 font-bold">TIM KANAN</span>
        </div>
      </div>
    </div>
  );
};

export default function TarikTambangMath() {
  // --- STATE ---
  const [gameState, setGameState] = useState('menu'); // menu, playing, round_result, game_over
  const [gameMode, setGameMode] = useState('1p'); // 1p, 2p
  const [questions, setQuestions] = useState([]);
  const [currentQIndex, setCurrentQIndex] = useState(0);
  const [timer, setTimer] = useState(300); // 5 minutes total in seconds
  
  // Game Logic State
  const [ropePosition, setRopePosition] = useState(0); // -5 to 5
  const [p1Input, setP1Input] = useState('');
  const [p2Input, setP2Input] = useState('');
  const [roundWinner, setRoundWinner] = useState(null); // 'p1', 'p2', or 'draw' (if timeout)
  const [feedback, setFeedback] = useState(null); // Feedback message

  // Bot State
  const botTimerRef = useRef(null);

  // --- INITIALIZATION ---
  const startGame = (mode) => {
    const qBank = generateQuestionBank();
    // Select 10 random questions
    const selectedQuestions = qBank.slice(0, 10);
    
    setQuestions(selectedQuestions);
    setGameMode(mode);
    setGameState('playing');
    setCurrentQIndex(0);
    setTimer(300); // 5 mins
    setRopePosition(0);
    setP1Input('');
    setP2Input('');
    setRoundWinner(null);
    setFeedback(null);
  };

  // --- GAME LOOP & TIMER ---
  useEffect(() => {
    let interval;
    if (gameState === 'playing' && timer > 0) {
      interval = setInterval(() => {
        setTimer((prev) => {
          if (prev <= 1) {
            endGame('timeout');
            return 0;
          }
          return prev - 1;
        });
      }, 1000);
    }
    return () => clearInterval(interval);
  }, [gameState, timer]);

  // --- BOT LOGIC (1 Player Mode) ---
  useEffect(() => {
    if (gameState === 'playing' && gameMode === '1p') {
      const currentQ = questions[currentQIndex];
      if (!currentQ) return;

      // Difficulty simulation: 
      // Bot answers between 3s and 8s.
      // 80% chance to be correct, 20% chance to be wrong (and then correct later).
      
      const delay = Math.random() * 4000 + 3000; // 3-7 seconds delay
      
      botTimerRef.current = setTimeout(() => {
        // Simple bot: just wins the round if player hasn't answered yet
        // In a real app, we'd simulate typing, but here we just trigger the check
        handleAnswer('p2', currentQ.ans); 
      }, delay);
    }
    return () => clearTimeout(botTimerRef.current);
  }, [gameState, currentQIndex, questions, gameMode]);

  // --- INPUT HANDLING ---
  const handleInput = (player, val) => {
    if (player === 'p1') {
      if (p1Input.length < 2) setP1Input(prev => prev + val);
    } else {
      if (p2Input.length < 2) setP2Input(prev => prev + val);
    }
  };

  const clearInput = (player) => {
    if (player === 'p1') setP1Input('');
    else setP2Input('');
  };

  const handleAnswer = (player, valueOrNull) => {
    const currentQ = questions[currentQIndex];
    const val = valueOrNull !== null ? valueOrNull : parseInt(player === 'p1' ? p1Input : p2Input);

    if (isNaN(val)) return;

    if (val === currentQ.ans) {
      // CORRECT ANSWER
      const newPos = player === 'p1' ? ropePosition - 1 : ropePosition + 1;
      setRopePosition(newPos);
      setRoundWinner(player);
      setFeedback(`${player === 'p1' ? 'Tim Kiri' : 'Tim Kanan'} Benar!`);
      
      // Clear bot timer immediately so it doesn't fire after round end
      if (botTimerRef.current) clearTimeout(botTimerRef.current);

      // Brief delay before next question
      setGameState('round_result');
      setTimeout(() => {
        nextRound(newPos);
      }, 1500);

    } else {
      // WRONG ANSWER
      // Penalty: Clear input and maybe shake screen (visual only)
      clearInput(player);
      // In a more complex version, maybe a time penalty
    }
  };

  const nextRound = (currentRopePos) => {
    // Check win condition by rope pull (Mercy rule)
    if (currentRopePos <= -5) {
        endGame('p1_win');
        return;
    }
    if (currentRopePos >= 5) {
        endGame('p2_win');
        return;
    }

    // Check if max questions reached
    if (currentQIndex >= 9) {
        // Game Over by rounds
        endGame('finished');
    } else {
        setCurrentQIndex(prev => prev + 1);
        setP1Input('');
        setP2Input('');
        setRoundWinner(null);
        setFeedback(null);
        setGameState('playing');
    }
  };

  const endGame = (reason) => {
    setGameState('game_over');
    setRoundWinner(reason); // Reuse state variable to store end reason
  };

  // --- RENDER HELPERS ---
  const formatTime = (seconds) => {
    const m = Math.floor(seconds / 60);
    const s = seconds % 60;
    return `${m}:${s < 10 ? '0' : ''}${s}`;
  };

  // --- RENDER VIEWS ---

  if (gameState === 'menu') {
    return (
      <div className={`min-h-screen ${COLORS.bg} flex flex-col items-center justify-center p-4 font-sans`}>
        <div className="bg-white p-8 rounded-3xl shadow-2xl border-b-8 border-yellow-400 max-w-lg w-full text-center">
          <div className="mb-6 flex justify-center">
             <div className="text-6xl animate-bounce">➰</div>
          </div>
          <h1 className="text-4xl font-extrabold text-blue-600 mb-2">Tarik Tambang</h1>
          <h2 className="text-2xl font-bold text-orange-500 mb-8">Matematika SD</h2>
          
          <div className="space-y-4">
            <button 
              onClick={() => startGame('1p')}
              className="w-full py-4 bg-blue-500 hover:bg-blue-600 text-white rounded-xl font-bold text-xl shadow-lg border-b-4 border-blue-700 active:border-b-0 active:translate-y-1 transition-all flex items-center justify-center gap-3"
            >
              <User size={28} />
              1 Pemain (vs Robot)
            </button>
            <button 
              onClick={() => startGame('2p')}
              className="w-full py-4 bg-red-500 hover:bg-red-600 text-white rounded-xl font-bold text-xl shadow-lg border-b-4 border-red-700 active:border-b-0 active:translate-y-1 transition-all flex items-center justify-center gap-3"
            >
              <Users size={28} />
              2 Pemain (Versus)
            </button>
          </div>

          <div className="mt-8 text-gray-500 text-sm">
            <p>Jawab cepat untuk menarik tali!</p>
            <p>Target: Penjumlahan sampai 20</p>
          </div>
        </div>
      </div>
    );
  }

  if (gameState === 'game_over') {
    let title = "";
    let sub = "";
    let color = "";
    let emoji = "";

    if (roundWinner === 'p1_win' || (roundWinner === 'finished' && ropePosition < 0)) {
        title = "TIM KIRI MENANG!";
        sub = "Luar biasa! Kamu sangat kuat!";
        color = "text-blue-600";
        emoji = "🐱🏆";
    } else if (roundWinner === 'p2_win' || (roundWinner === 'finished' && ropePosition > 0)) {
        title = gameMode === '1p' ? "ROBOT MENANG!" : "TIM KANAN MENANG!";
        sub = "Coba lagi ya!";
        color = "text-red-600";
        emoji = "🐶🏆";
    } else {
        title = "SERI!";
        sub = "Kekuatan kalian seimbang!";
        color = "text-purple-600";
        emoji = "🤝";
    }

    return (
      <div className={`min-h-screen ${COLORS.bg} flex flex-col items-center justify-center p-4`}>
        <div className="bg-white p-8 rounded-3xl shadow-2xl border-4 border-gray-200 text-center max-w-md w-full animate-fade-in-up">
          <div className="text-8xl mb-4">{emoji}</div>
          <h1 className={`text-3xl font-extrabold ${color} mb-2`}>{title}</h1>
          <p className="text-gray-600 font-bold mb-6">{sub}</p>
          
          <div className="bg-gray-100 p-4 rounded-xl mb-6">
             <p className="text-sm text-gray-500 uppercase font-bold">Posisi Akhir Tali</p>
             <div className="flex justify-between items-center mt-2 px-4 font-mono font-bold text-xl">
                <span className="text-blue-500">{5 + Math.abs(Math.min(0, ropePosition))}</span>
                <span className="text-gray-400">-</span>
                <span className="text-red-500">{5 + Math.max(0, ropePosition)}</span>
             </div>
          </div>

          <button 
            onClick={() => setGameState('menu')}
            className="w-full py-4 bg-green-500 hover:bg-green-600 text-white rounded-xl font-bold text-xl shadow-lg flex items-center justify-center gap-2"
          >
            <RefreshCw /> Main Lagi
          </button>
        </div>
      </div>
    );
  }

  // --- PLAYING STATE ---
  const currentQ = questions[currentQIndex];

  return (
    <div className={`min-h-screen ${COLORS.bg} flex flex-col overflow-hidden`}>
      {/* HEADER */}
      <header className="bg-white p-2 shadow-md flex justify-between items-center px-4 md:px-8 z-20">
        <div className="flex items-center gap-2 bg-gray-100 px-4 py-2 rounded-full font-bold text-gray-700">
           <Clock size={20} className="text-orange-500"/>
           <span>{formatTime(timer)}</span>
        </div>
        
        <div className="text-xl font-extrabold tracking-widest text-amber-600">
            SOAL {currentQIndex + 1}/10
        </div>

        <button onClick={() => setGameState('menu')} className="p-2 bg-gray-100 rounded-full hover:bg-gray-200 text-gray-600">
            <RefreshCw size={20}/>
        </button>
      </header>

      {/* GAME AREA */}
      <main className="flex-1 flex flex-col max-w-6xl mx-auto w-full p-2 md:p-4">
        
        {/* SCOREBOARD / STATUS */}
        <div className="text-center mb-2 h-8">
            {feedback && (
                <span className="inline-block bg-yellow-400 text-yellow-900 px-6 py-1 rounded-full font-bold animate-pulse shadow-sm">
                    {feedback}
                </span>
            )}
        </div>

        {/* ROPE VISUALIZATION */}
        <RopeArena position={ropePosition} winner={roundWinner} />

        {/* QUESTION DISPLAY */}
        <div className="flex justify-center my-4">
            <div className="bg-white border-4 border-amber-400 px-12 py-6 rounded-2xl shadow-xl transform rotate-1 hover:rotate-0 transition-transform">
                <h2 className="text-5xl md:text-6xl font-black text-gray-800 tracking-wider">
                    {currentQ.a} + {currentQ.b} = ?
                </h2>
            </div>
        </div>

        {/* CONTROLS */}
        <div className="flex-1 flex flex-row gap-4 md:gap-12 items-end justify-center pb-4">
            {/* PLAYER 1 (LEFT) */}
            <div className="flex-1 flex justify-end">
                <Keypad 
                    label={gameMode === '1p' ? "Kamu (Tim Kiri)" : "Pemain 1 (Kiri)"}
                    colorTheme={{
                        main: 'bg-blue-500', 
                        hover: 'hover:bg-blue-600', 
                        bg: 'bg-blue-50', 
                        border: 'border-blue-200',
                        text: 'text-blue-700'
                    }}
                    currentValue={p1Input}
                    onInput={(v) => handleInput('p1', v)}
                    onClear={() => clearInput('p1')}
                    onSubmit={() => handleAnswer('p1', null)}
                    disabled={gameState === 'round_result'}
                />
            </div>

            {/* PLAYER 2 (RIGHT) */}
            <div className="flex-1 flex justify-start">
                 {gameMode === '2p' ? (
                    <Keypad 
                        label="Pemain 2 (Kanan)"
                        colorTheme={{
                            main: 'bg-red-500', 
                            hover: 'hover:bg-red-600', 
                            bg: 'bg-red-50', 
                            border: 'border-red-200',
                            text: 'text-red-700'
                        }}
                        currentValue={p2Input}
                        onInput={(v) => handleInput('p2', v)}
                        onClear={() => clearInput('p2')}
                        onSubmit={() => handleAnswer('p2', null)}
                        disabled={gameState === 'round_result'}
                    />
                 ) : (
                    /* BOT DISPLAY for 1P Mode */
                    <div className="w-full max-w-sm h-full flex flex-col justify-end opacity-80 pointer-events-none grayscale">
                         <div className="bg-white border-4 border-gray-300 p-6 rounded-xl text-center shadow-lg">
                            <div className="text-4xl mb-2">🤖</div>
                            <h3 className="font-bold text-gray-500">Robot Sedang Berpikir...</h3>
                            <div className="flex justify-center gap-1 mt-3">
                                <div className="w-2 h-2 bg-gray-400 rounded-full animate-bounce" style={{animationDelay: '0s'}}></div>
                                <div className="w-2 h-2 bg-gray-400 rounded-full animate-bounce" style={{animationDelay: '0.2s'}}></div>
                                <div className="w-2 h-2 bg-gray-400 rounded-full animate-bounce" style={{animationDelay: '0.4s'}}></div>
                            </div>
                         </div>
                    </div>
                 )}
            </div>
        </div>
      </main>

      {/* FOOTER INSTRUCTIONS */}
      <footer className="bg-white/50 p-2 text-center text-xs text-gray-500 font-bold uppercase tracking-widest">
         {gameMode === '2p' ? "Duel Teman Sebangku" : "Latih Kecepatanmu!"}
      </footer>
    </div>
  );
}
