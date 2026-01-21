<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Kanit', sans-serif;
    }
    
    .coin-spin {
      animation: spin 2s linear infinite;
    }
    
    @keyframes spin {
      from { transform: rotateY(0deg); }
      to { transform: rotateY(360deg); }
    }
    
    .bounce-in {
      animation: bounceIn 0.5s ease-out;
    }
    
    @keyframes bounceIn {
      0% { transform: scale(0); opacity: 0; }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); opacity: 1; }
    }
    
    .float {
      animation: float 3s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    
    .sparkle {
      animation: sparkle 1.5s ease-in-out infinite;
    }
    
    @keyframes sparkle {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(1.2); }
    }
    
    .progress-fill {
      transition: width 0.5s ease-out;
    }
    
    .card-hover {
      transition: all 0.3s ease;
    }
    
    .card-hover:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full w-full overflow-auto" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);"><!-- ����้าหลัก -->
   <div id="home-screen" class="min-h-full p-4 md:p-8">
    <div class="max-w-4xl mx-auto"><!-- Header -->
     <div class="text-center mb-8">
      <div class="inline-block float">
       <svg class="w-20 h-20 mx-auto mb-4" viewbox="0 0 100 100"><circle cx="50" cy="50" r="45" fill="#FFD700" stroke="#FFA500" stroke-width="4" /> <text x="50" y="58" text-anchor="middle" font-size="28" font-weight="bold" fill="#8B4513">
         ฿
        </text> <circle cx="50" cy="50" r="38" fill="none" stroke="#FFA500" stroke-width="2" stroke-dasharray="5,5" />
       </svg>
      </div>
      <h1 id="app-title" class="text-3xl md:text-4xl font-bold text-white mb-2 drop-shadow-lg">คณิตศาสตร์การเงิน ป.5</h1>
      <p id="welcome-message" class="text-lg text-white/90">เรียนรู้เรื่องเงินให้สนุก!</p>
     </div><!-- เมนูหลัก -->
     <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-8"><!-- บทเรียน --> <button onclick="showSection('lessons')" class="card-hover bg-white/95 backdrop-blur rounded-3xl p-6 text-left shadow-xl">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-green-400 to-green-600 rounded-2xl flex items-center justify-center"><span class="text-3xl">📚</span>
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">บทเรียน</h3>
         <p class="text-gray-600">เรียนรู้เรื่องเงินและการคำนวณ</p>
        </div>
       </div></button> <!-- แบบฝึกหัด --> <button onclick="showSection('practice')" class="card-hover bg-white/95 backdrop-blur rounded-3xl p-6 text-left shadow-xl">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-blue-400 to-blue-600 rounded-2xl flex items-center justify-center"><span class="text-3xl">✏️</span>
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">แบบฝึกหัด</h3>
         <p class="text-gray-600">ฝึกทักษะการคิดเลข</p>
        </div>
       </div></button> <!-- เกมสนุก --> <button onclick="showSection('games')" class="card-hover bg-white/95 backdrop-blur rounded-3xl p-6 text-left shadow-xl">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-purple-400 to-purple-600 rounded-2xl flex items-center justify-center"><span class="text-3xl">🎮</span>
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">เกมสนุก</h3>
         <p class="text-gray-600">เล่นเกมคำนวณเงิน</p>
        </div>
       </div></button> <!-- ร้านค้าจำลอง --> <button onclick="showSection('shop')" class="card-hover bg-white/95 backdrop-blur rounded-3xl p-6 text-left shadow-xl">
       <div class="flex items-center gap-4">
        <div class="w-16 h-16 bg-gradient-to-br from-orange-400 to-orange-600 rounded-2xl flex items-center justify-center"><span class="text-3xl">🏪</span>
        </div>
        <div>
         <h3 class="text-xl font-bold text-gray-800">ร้านค้าจำลอง</h3>
         <p class="text-gray-600">ฝึกซื้อขายและทอนเงิน</p>
        </div>
       </div></button>
     </div><!-- คะแนนสะสม -->
     <div class="bg-white/20 backdrop-blur rounded-2xl p-4 text-center">
      <div class="flex items-center justify-center gap-2 mb-2"><span class="text-2xl sparkle">⭐</span> <span class="text-white font-bold text-lg">คะแนนสะสม: <span id="total-score">0</span> คะแนน</span> <span class="text-2xl sparkle">⭐</span>
      </div>
      <div class="w-full bg-white/30 rounded-full h-3">
       <div id="progress-bar" class="progress-fill bg-yellow-400 h-3 rounded-full" style="width: 0%"></div>
      </div>
      <p class="text-white/80 text-sm mt-1">เก็บครบ 100 คะแนนเพื่อรับเหรียญทอง!</p>
     </div><!-- ชื่อผู้สร้าง -->
     <div class="mt-6 text-center">
      <div class="inline-block bg-white/30 backdrop-blur rounded-2xl px-6 py-3">
       <p class="text-white/70 text-sm mb-1">ออกแบบและพัฒนาโดย</p>
       <p class="text-white font-bold text-lg">เด็กหญิงอัญรินทร์ สิงหรัตน์</p>
       <p class="text-white/90 text-sm">ชั้นประถมศึกษาปีที่ 5</p>
      </div>
     </div>
    </div>
   </div><!-- หน้าบทเรียน -->
   <div id="lessons-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-4xl mx-auto"><button onclick="showSection('home')" class="mb-6 bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-full flex items-center gap-2 transition-all"> <span>←</span> กลับหน้าหลัก </button>
     <h2 class="text-2xl font-bold text-white mb-6 text-center">📚 บทเรียนการเงิน</h2>
     <div class="space-y-4"><!-- บทเรียน 1 -->
      <div class="bg-white/95 rounded-2xl p-6 shadow-xl">
       <h3 class="text-xl font-bold text-gray-800 mb-4 flex items-center gap-2"><span class="w-8 h-8 bg-green-500 text-white rounded-full flex items-center justify-center text-sm">1</span> รู้จักธนบัตรและเหรียญ</h3>
       <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <div class="bg-gradient-to-br from-green-100 to-green-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          💵
         </div>
         <p class="font-bold text-green-800">1,000 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-purple-100 to-purple-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          💴
         </div>
         <p class="font-bold text-purple-800">500 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-red-100 to-red-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          💵
         </div>
         <p class="font-bold text-red-800">100 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-blue-100 to-blue-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          💴
         </div>
         <p class="font-bold text-blue-800">50 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-yellow-100 to-yellow-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          💰
         </div>
         <p class="font-bold text-yellow-800">20 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-gray-100 to-gray-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          🪙
         </div>
         <p class="font-bold text-gray-800">10 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-amber-100 to-amber-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          🪙
         </div>
         <p class="font-bold text-amber-800">5 บาท</p>
        </div>
        <div class="bg-gradient-to-br from-orange-100 to-orange-200 p-4 rounded-xl text-center">
         <div class="text-3xl mb-2">
          🪙
         </div>
         <p class="font-bold text-orange-800">1 บาท</p>
        </div>
       </div>
      </div><!-- บทเรียน 2 -->
      <div class="bg-white/95 rounded-2xl p-6 shadow-xl">
       <h3 class="text-xl font-bold text-gray-800 mb-4 flex items-center gap-2"><span class="w-8 h-8 bg-blue-500 text-white rounded-full flex items-center justify-center text-sm">2</span> การบวกและลบเงิน</h3>
       <div class="bg-blue-50 p-4 rounded-xl">
        <p class="text-gray-700 mb-2"><strong>ตัวอย่าง:</strong> น้องมีเงิน 50 บาท แม่ให้อีก 30 บาท น้องมีเงินทั้งหมดเท่าไร?</p>
        <p class="text-blue-600 font-bold">วิธีคิด: 50 + 30 = 80 บาท</p>
       </div>
      </div><!-- บทเรียน 3 -->
      <div class="bg-white/95 rounded-2xl p-6 shadow-xl">
       <h3 class="text-xl font-bold text-gray-800 mb-4 flex items-center gap-2"><span class="w-8 h-8 bg-purple-500 text-white rounded-full flex items-center justify-center text-sm">3</span> การทอนเงิน</h3>
       <div class="bg-purple-50 p-4 rounded-xl">
        <p class="text-gray-700 mb-2"><strong>ตัวอย่าง:</strong> ซื้อขนม 35 บาท จ่ายเงิน 50 บาท จะได้เงินทอนเท่าไร?</p>
        <p class="text-purple-600 font-bold">วิธีคิด: 50 - 35 = 15 บาท</p>
       </div>
      </div>
     </div>
    </div>
   </div><!-- หน้าแบบฝึกหัด -->
   <div id="practice-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><button onclick="showSection('home')" class="mb-6 bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-full flex items-center gap-2 transition-all"> <span>←</span> กลับหน้าหลัก </button>
     <div class="bg-white/95 rounded-3xl p-6 shadow-xl">
      <div class="text-center mb-6">
       <h2 class="text-2xl font-bold text-gray-800">✏️ แบบฝึกหัด</h2>
       <p class="text-gray-600">ข้อที่ <span id="question-num">1</span>/10</p>
      </div>
      <div id="practice-question" class="bg-gradient-to-br from-blue-50 to-purple-50 p-6 rounded-2xl mb-6">
       <p class="text-lg text-gray-800 text-center" id="question-text">กำลังโหลดคำถาม...</p>
      </div>
      <div id="practice-options" class="grid grid-cols-2 gap-4 mb-6"><!-- Options will be generated here -->
      </div>
      <div id="practice-feedback" class="hidden text-center p-4 rounded-xl mb-4"><!-- Feedback will appear here -->
      </div>
      <div class="flex justify-center gap-4"><button onclick="generatePracticeQuestion()" id="next-btn" class="hidden bg-gradient-to-r from-green-500 to-green-600 hover:from-green-600 hover:to-green-700 text-white px-8 py-3 rounded-full font-bold transition-all"> ข้อถัดไป → </button>
      </div>
     </div>
    </div>
   </div><!-- หน้าเกม -->
   <div id="games-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><button onclick="showSection('home')" class="mb-6 bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-full flex items-center gap-2 transition-all"> <span>←</span> กลับหน้าหลัก </button>
     <div class="bg-white/95 rounded-3xl p-6 shadow-xl">
      <div class="text-center mb-6">
       <h2 class="text-2xl font-bold text-gray-800">🎮 เกมนับเงินเร็ว</h2>
       <p class="text-gray-600">นับเงินให้ถูกต้องภายในเวลา!</p>
      </div>
      <div class="flex justify-between items-center mb-6 bg-gray-100 p-4 rounded-xl">
       <div class="text-center">
        <p class="text-sm text-gray-600">��️ เวลา</p>
        <p class="text-2xl font-bold text-blue-600" id="game-timer">30</p>
       </div>
       <div class="text-center">
        <p class="text-sm text-gray-600">🎯 คะแนน</p>
        <p class="text-2xl font-bold text-green-600" id="game-score">0</p>
       </div>
      </div>
      <div id="game-area" class="bg-gradient-to-br from-yellow-50 to-orange-50 p-6 rounded-2xl mb-6">
       <div id="money-display" class="flex flex-wrap justify-center gap-2 mb-4 min-h-24"><!-- Money items will appear here -->
       </div>
       <p class="text-center text-gray-700">รวมเงินทั้งหมดเท่าไร?</p>
      </div>
      <div id="game-input" class="mb-6">
       <div class="flex gap-2 justify-center"><input type="number" id="game-answer" class="w-32 px-4 py-3 border-2 border-gray-300 rounded-xl text-center text-xl font-bold focus:border-purple-500 focus:outline-none" placeholder="?"> <span class="flex items-center text-xl font-bold text-gray-700">บาท</span>
       </div>
      </div>
      <div class="flex justify-center gap-4"><button onclick="checkGameAnswer()" id="submit-game-btn" class="bg-gradient-to-r from-purple-500 to-purple-600 hover:from-purple-600 hover:to-purple-700 text-white px-8 py-3 rounded-full font-bold transition-all"> ตรวจคำตอบ </button> <button onclick="startGame()" id="start-game-btn" class="bg-gradient-to-r from-green-500 to-green-600 hover:from-green-600 hover:to-green-700 text-white px-8 py-3 rounded-full font-bold transition-all"> เริ่มเกมใหม่ </button>
      </div>
     </div>
    </div>
   </div><!-- หน้าร้านค้าจำลอง -->
   <div id="shop-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-4xl mx-auto"><button onclick="showSection('home')" class="mb-6 bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-full flex items-center gap-2 transition-all"> <span>←</span> กลับหน้าหลัก </button>
     <div class="bg-white/95 rounded-3xl p-6 shadow-xl">
      <div class="text-center mb-6">
       <h2 class="text-2xl font-bold text-gray-800">🏪 ร้านค้าจำลอง</h2>
       <div class="flex justify-center items-center gap-2 mt-2"><span class="text-lg">💰 เงินของฉัน:</span> <span class="text-2xl font-bold text-green-600" id="my-money">100</span> <span class="text-lg">บาท</span>
       </div>
      </div><!-- สินค้า -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-6">
       <div class="shop-item bg-gradient-to-br from-pink-50 to-pink-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🍬 ลูกอม', 5)">
        <div class="text-4xl mb-2">
         🍬
        </div>
        <p class="font-bold text-gray-800">ลูกอม</p>
        <p class="text-pink-600 font-bold">5 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-yellow-50 to-yellow-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🍪 คุกกี้', 15)">
        <div class="text-4xl mb-2">
         🍪
        </div>
        <p class="font-bold text-gray-800">คุกกี้</p>
        <p class="text-yellow-600 font-bold">15 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-blue-50 to-blue-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🧃 น้ำผลไม้', 20)">
        <div class="text-4xl mb-2">
         🧃
        </div>
        <p class="font-bold text-gray-800">น้ำผลไม้</p>
        <p class="text-blue-600 font-bold">20 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-orange-50 to-orange-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🍕 พิซซ่า', 45)">
        <div class="text-4xl mb-2">
         🍕
        </div>
        <p class="font-bold text-gray-800">พิซซ่า</p>
        <p class="text-orange-600 font-bold">45 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-green-50 to-green-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🍎 แอปเปิ้ล', 25)">
        <div class="text-4xl mb-2">
         🍎
        </div>
        <p class="font-bold text-gray-800">แอปเปิ้ล</p>
        <p class="text-green-600 font-bold">25 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-purple-50 to-purple-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('🍦 ไอศกรีม', 30)">
        <div class="text-4xl mb-2">
         🍦
        </div>
        <p class="font-bold text-gray-800">ไอศกรีม</p>
        <p class="text-purple-600 font-bold">30 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-red-50 to-red-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('📓 สมุด', 35)">
        <div class="text-4xl mb-2">
         📓
        </div>
        <p class="font-bold text-gray-800">สมุด</p>
        <p class="text-red-600 font-bold">35 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-teal-50 to-teal-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="buyItem('✏️ ดินสอ', 10)">
        <div class="text-4xl mb-2">
         ✏️
        </div>
        <p class="font-bold text-gray-800">ดินสอ</p>
        <p class="text-teal-600 font-bold">10 บาท</p>
       </div>
      </div><!-- ตะกร้า -->
      <div class="bg-gray-100 p-4 rounded-xl mb-4">
       <h3 class="font-bold text-gray-800 mb-2">🛒 ตะกร้าสินค้า</h3>
       <div id="cart-items" class="min-h-12 text-gray-600">
        ยังไม่มีสินค้าในตะกร้า
       </div>
       <div class="flex justify-between items-center mt-4 pt-4 border-t border-gray-300"><span class="font-bold">รวมทั้งหมด:</span> <span class="text-xl font-bold text-purple-600"><span id="cart-total">0</span> บาท</span>
       </div>
      </div><!-- ปุ่มดำเนินการ -->
      <div class="flex justify-center gap-4"><button onclick="checkout()" class="bg-gradient-to-r from-green-500 to-green-600 hover:from-green-600 hover:to-green-700 text-white px-6 py-3 rounded-full font-bold transition-all"> 💳 ชำระเงิน </button> <button onclick="clearCart()" class="bg-gradient-to-r from-red-500 to-red-600 hover:from-red-600 hover:to-red-700 text-white px-6 py-3 rounded-full font-bold transition-all"> ���️ ล้างตะกร้า </button> <button onclick="resetShop()" class="bg-gradient-to-r from-blue-500 to-blue-600 hover:from-blue-600 hover:to-blue-700 text-white px-6 py-3 rounded-full font-bold transition-all"> 🔄 เริ่มใหม่ </button>
      </div><!-- ��้อความแจ้งเตือน -->
      <div id="shop-message" class="hidden mt-4 p-4 rounded-xl text-center font-bold"></div>
     </div>
    </div>
   </div>
  </div>
  <script>
    // Default config
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'เรียนรู้เรื่องเงินให้สนุก!',
      background_color: '#7dd3fc',
      surface_color: '#ffffff',
      text_color: '#1f2937',
      primary_action_color: '#8b5cf6',
      secondary_action_color: '#10b981'
    };

    let config = { ...defaultConfig };
    let totalScore = 0;
    let practiceQuestionNum = 1;
    let currentAnswer = 0;
    let cart = [];
    let myMoney = 100;
    let gameTimer = null;
    let gameTimeLeft = 30;
    let gameScore = 0;
    let currentMoneyTotal = 0;

    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (newConfig) => {
          config = { ...defaultConfig, ...newConfig };
          applyConfig();
        },
        mapToCapabilities: (cfg) => ({
          recolorables: [
            {
              get: () => cfg.background_color || defaultConfig.background_color,
              set: (value) => { cfg.background_color = value; window.elementSdk.setConfig({ background_color: value }); }
            },
            {
              get: () => cfg.surface_color || defaultConfig.surface_color,
              set: (value) => { cfg.surface_color = value; window.elementSdk.setConfig({ surface_color: value }); }
            },
            {
              get: () => cfg.text_color || defaultConfig.text_color,
              set: (value) => { cfg.text_color = value; window.elementSdk.setConfig({ text_color: value }); }
            },
            {
              get: () => cfg.primary_action_color || defaultConfig.primary_action_color,
              set: (value) => { cfg.primary_action_color = value; window.elementSdk.setConfig({ primary_action_color: value }); }
            },
            {
              get: () => cfg.secondary_action_color || defaultConfig.secondary_action_color,
              set: (value) => { cfg.secondary_action_color = value; window.elementSdk.setConfig({ secondary_action_color: value }); }
            }
          ],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (cfg) => new Map([
          ['app_title', cfg.app_title || defaultConfig.app_title],
          ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
        ])
      });
    }

    function applyConfig() {
      // Apply text content
      document.getElementById('app-title').textContent = config.app_title || defaultConfig.app_title;
      document.getElementById('welcome-message').textContent = config.welcome_message || defaultConfig.welcome_message;
      
      // Apply colors
      const app = document.getElementById('app');
      const bgColor = config.background_color || defaultConfig.background_color;
      app.style.background = `linear-gradient(135deg, ${bgColor} 0%, ${adjustColor(bgColor, -20)} 50%, ${adjustColor(bgColor, 30)} 100%)`;
    }

    function adjustColor(hex, amount) {
      const num = parseInt(hex.replace('#', ''), 16);
      const r = Math.min(255, Math.max(0, (num >> 16) + amount));
      const g = Math.min(255, Math.max(0, ((num >> 8) & 0x00FF) + amount));
      const b = Math.min(255, Math.max(0, (num & 0x0000FF) + amount));
      return '#' + (0x1000000 + (r << 16) + (g << 8) + b).toString(16).slice(1);
    }

    // Navigation
    function showSection(section) {
      const screens = ['home', 'lessons', 'practice', 'games', 'shop'];
      screens.forEach(s => {
        document.getElementById(s + '-screen').classList.add('hidden');
      });
      document.getElementById(section + '-screen').classList.remove('hidden');
      
      if (section === 'practice') {
        practiceQuestionNum = 1;
        generatePracticeQuestion();
      } else if (section === 'games') {
        startGame();
      }
    }

    // Practice Questions
    const questions = [
      { type: 'add', text: 'น้องมีเงิน {a} บาท พ่อให้อีก {b} บาท น้องมีเงินทั้งหมดเท่าไร?' },
      { type: 'subtract', text: 'พี่มีเงิน {a} บาท ซื้อขนม {b} บาท พี่เหลือเงินเท่าไร?' },
      { type: 'change', text: 'ซื้อของ {b} บาท จ่าย {a} บาท ได้เงินทอนเท่าไ���?' },
      { type: 'add', text: 'แม่ให้เงิน {a} บาท ยายให้อีก {b} บาท ได้เงินทั้งหมดเท่าไร?' },
      { type: 'subtract', text: 'มีเงินเก็บ {a} บาท ใช้ไป {b} บาท เหลือเงินเท่าไร?' }
    ];

    function generatePracticeQuestion() {
      const q = questions[Math.floor(Math.random() * questions.length)];
      let a, b, answer;
      
      if (q.type === 'add') {
        a = Math.floor(Math.random() * 50) * 10 + 10;
        b = Math.floor(Math.random() * 30) * 10 + 10;
        answer = a + b;
      } else if (q.type === 'subtract') {
        a = Math.floor(Math.random() * 50) * 10 + 100;
        b = Math.floor(Math.random() * 30) * 10 + 10;
        if (b >= a) b = a - 10;
        answer = a - b;
      } else {
        b = Math.floor(Math.random() * 30) * 10 + 20;
        a = Math.ceil(b / 100) * 100;
        if (a === b) a += 100;
        answer = a - b;
      }
      
      currentAnswer = answer;
      
      const text = q.text.replace('{a}', a).replace('{b}', b);
      document.getElementById('question-text').textContent = text;
      document.getElementById('question-num').textContent = practiceQuestionNum;
      
      // Generate options
      const options = [answer];
      while (options.length < 4) {
        const wrong = answer + (Math.floor(Math.random() * 6) - 3) * 10;
        if (wrong > 0 && !options.includes(wrong)) {
          options.push(wrong);
        }
      }
      options.sort(() => Math.random() - 0.5);
      
      const optionsContainer = document.getElementById('practice-options');
      optionsContainer.innerHTML = options.map(opt => `
        <button onclick="checkPracticeAnswer(${opt})" class="option-btn bg-white border-2 border-gray-300 hover:border-purple-500 hover:bg-purple-50 p-4 rounded-xl text-xl font-bold text-gray-800 transition-all">
          ${opt} บาท
        </button>
      `).join('');
      
      document.getElementById('practice-feedback').classList.add('hidden');
      document.getElementById('next-btn').classList.add('hidden');
    }

    function checkPracticeAnswer(selected) {
      const feedback = document.getElementById('practice-feedback');
      const buttons = document.querySelectorAll('.option-btn');
      
      buttons.forEach(btn => {
        btn.disabled = true;
        if (parseInt(btn.textContent) === currentAnswer) {
          btn.classList.add('bg-green-100', 'border-green-500');
        }
        if (parseInt(btn.textContent) === selected && selected !== currentAnswer) {
          btn.classList.add('bg-red-100', 'border-red-500');
        }
      });
      
      if (selected === currentAnswer) {
        feedback.innerHTML = '<span class="text-green-600">🎉 ถูกต้อง! เก่งมาก!</span>';
        feedback.className = 'bg-green-100 text-center p-4 rounded-xl mb-4 bounce-in';
        addScore(10);
      } else {
        feedback.innerHTML = `<span class="text-red-600">❌ ไม่ถูกต้อง คำตอบคือ ${currentAnswer} บาท</span>`;
        feedback.className = 'bg-red-100 text-center p-4 rounded-xl mb-4 bounce-in';
      }
      
      feedback.classList.remove('hidden');
      
      if (practiceQuestionNum < 10) {
        practiceQuestionNum++;
        document.getElementById('next-btn').classList.remove('hidden');
      } else {
        document.getElementById('next-btn').textContent = 'เริ่มใหม่';
        document.getElementById('next-btn').onclick = () => {
          practiceQuestionNum = 1;
          document.getElementById('next-btn').textContent = 'ข้อถัดไป →';
          document.getElementById('next-btn').onclick = generatePracticeQuestion;
          generatePracticeQuestion();
        };
        document.getElementById('next-btn').classList.remove('hidden');
      }
    }

    // Game
    const moneyValues = [
      { value: 1000, emoji: '💵', color: 'green' },
      { value: 500, emoji: '💴', color: 'purple' },
      { value: 100, emoji: '💵', color: 'red' },
      { value: 50, emoji: '💴', color: 'blue' },
      { value: 20, emoji: '💵', color: 'green' },
      { value: 10, emoji: '🪙', color: 'gray' },
      { value: 5, emoji: '🪙', color: 'amber' },
      { value: 1, emoji: '🪙', color: 'orange' }
    ];

    function startGame() {
      gameTimeLeft = 30;
      gameScore = 0;
      document.getElementById('game-timer').textContent = gameTimeLeft;
      document.getElementById('game-score').textContent = gameScore;
      document.getElementById('game-answer').value = '';
      
      if (gameTimer) clearInterval(gameTimer);
      
      generateMoneyQuestion();
      
      gameTimer = setInterval(() => {
        gameTimeLeft--;
        document.getElementById('game-timer').textContent = gameTimeLeft;
        
        if (gameTimeLeft <= 0) {
          clearInterval(gameTimer);
          endGame();
        }
      }, 1000);
    }

    function generateMoneyQuestion() {
      const moneyDisplay = document.getElementById('money-display');
      moneyDisplay.innerHTML = '';
      currentMoneyTotal = 0;
      
      const numItems = Math.floor(Math.random() * 4) + 2;
      const selectedMoney = [];
      
      for (let i = 0; i < numItems; i++) {
        const money = moneyValues[Math.floor(Math.random() * moneyValues.length)];
        selectedMoney.push(money);
        currentMoneyTotal += money.value;
      }
      
      selectedMoney.forEach(money => {
        const div = document.createElement('div');
        div.className = `bg-${money.color}-100 px-3 py-2 rounded-lg text-center bounce-in`;
        div.innerHTML = `<span class="text-2xl">${money.emoji}</span><p class="text-sm font-bold">${money.value}฿</p>`;
        moneyDisplay.appendChild(div);
      });
      
      document.getElementById('game-answer').value = '';
      document.getElementById('game-answer').focus();
    }

    function checkGameAnswer() {
      const answer = parseInt(document.getElementById('game-answer').value);
      
      if (answer === currentMoneyTotal) {
        gameScore += 10;
        document.getElementById('game-score').textContent = gameScore;
        generateMoneyQuestion();
      } else {
        document.getElementById('game-answer').classList.add('border-red-500');
        setTimeout(() => {
          document.getElementById('game-answer').classList.remove('border-red-500');
        }, 500);
      }
    }

    function endGame() {
      const moneyDisplay = document.getElementById('money-display');
      moneyDisplay.innerHTML = `
        <div class="text-center">
          <p class="text-2xl mb-2">⏰ หมดเวลา!</p>
          <p class="text-xl font-bold text-purple-600">คุณได้ ${gameScore} คะแนน</p>
        </div>
      `;
      addScore(gameScore);
    }

    // Shop
    function buyItem(name, price) {
      cart.push({ name, price });
      updateCart();
    }

    function updateCart() {
      const cartItems = document.getElementById('cart-items');
      const cartTotal = document.getElementById('cart-total');
      
      if (cart.length === 0) {
        cartItems.innerHTML = 'ยังไม่มีสินค้าในตะกร้า';
        cartTotal.textContent = '0';
        return;
      }
      
      const itemCounts = {};
      cart.forEach(item => {
        if (!itemCounts[item.name]) {
          itemCounts[item.name] = { count: 0, price: item.price };
        }
        itemCounts[item.name].count++;
      });
      
      cartItems.innerHTML = Object.entries(itemCounts).map(([name, data]) => 
        `<div class="flex justify-between py-1">
          <span>${name} x${data.count}</span>
          <span class="font-bold">${data.price * data.count} บาท</span>
        </div>`
      ).join('');
      
      const total = cart.reduce((sum, item) => sum + item.price, 0);
      cartTotal.textContent = total;
    }

    function clearCart() {
      cart = [];
      updateCart();
      showShopMessage('ล้างตะกร้าแล้ว!', 'blue');
    }

    function checkout() {
      const total = cart.reduce((sum, item) => sum + item.price, 0);
      
      if (cart.length === 0) {
        showShopMessage('กรุณาเลือกสินค้าก่อนชำระเงิน', 'yellow');
        return;
      }
      
      if (total > myMoney) {
        showShopMessage(`เงินไม่พอ! ต้องการ ${total} บาท ��ต่มีแค่ ${myMoney} บาท`, 'red');
        return;
      }
      
      const change = myMoney - total;
      myMoney -= total;
      document.getElementById('my-money').textContent = myMoney;
      
      showShopMessage(`🎉 ซื้อสำเร็จ! จ่าย ${total} บาท ได้เงินทอน ${change} บาท`, 'green');
      addScore(5);
      cart = [];
      updateCart();
    }

    function resetShop() {
      myMoney = 100;
      cart = [];
      document.getElementById('my-money').textContent = myMoney;
      updateCart();
      showShopMessage('เริ่มต้นใหม่แล้ว! มีเงิน 100 บาท', 'blue');
    }

    function showShopMessage(text, color) {
      const msg = document.getElementById('shop-message');
      msg.textContent = text;
      msg.className = `mt-4 p-4 rounded-xl text-center font-bold bounce-in bg-${color}-100 text-${color}-800`;
      msg.classList.remove('hidden');
      
      setTimeout(() => {
        msg.classList.add('hidden');
      }, 3000);
    }

    // Score system
    function addScore(points) {
      totalScore += points;
      document.getElementById('total-score').textContent = totalScore;
      
      const progress = Math.min(totalScore, 100);
      document.getElementById('progress-bar').style.width = progress + '%';
    }

    // Handle enter key in game
    document.getElementById('game-answer').addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        checkGameAnswer();
      }
    });

    // Initialize
    applyConfig();
    showSection('home');
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c133c84360b731f',t:'MTc2ODk2MTAyMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
