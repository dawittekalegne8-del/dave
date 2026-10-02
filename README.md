```html
<!DOCTYPE html>
<html lang="am" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>et.brokers - ምርጥ የሪል ስቴት እና ቦታ መገበያያ</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
        }
        .fade-in {
            animation: fadeIn 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .hidden-section { display: none; }
    </style>
</head>
<body class="text-gray-900 antialiased flex flex-col min-h-screen">

    <nav class="bg-gradient-to-r from-red-900 via-rose-900 to-red-950 text-white shadow-2xl sticky top-0 z-50 border-b border-red-800/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-20 items-center">
                <!-- Professional Logo -->
                <div class="flex items-center space-x-3 cursor-pointer group" onclick="showSection('homeSection')">
                    <div class="w-12 h-12 bg-gradient-to-br from-yellow-400 to-amber-500 rounded-2xl shadow-xl flex items-center justify-center transform group-hover:scale-105 transition duration-300 border border-yellow-300">
                        <i class="fas fa-city text-red-950 text-2xl"></i>
                    </div>
                    <div>
                        <span class="font-black text-2xl tracking-tight text-white flex items-center">
                            et<span class="text-yellow-400">.</span>brokers
                        </span>
                        <span class="text-[10px] tracking-widest text-red-200 block uppercase font-bold">የኢትዮጵያ ንብረት ገበያ</span>
                    </div>
                </div>

                <!-- Navigation Links -->
                <div class="flex items-center space-x-2 sm:space-x-4">
                    <button onclick="showSection('homeSection')" class="px-3.5 py-2 rounded-xl font-semibold hover:bg-white/10 transition flex items-center gap-2 text-sm sm:text-base text-yellow-300 bg-white/5 border border-white/10">
                        <i class="fas fa-home"></i> ቤቶች እና ቦታዎች
                    </button>
                    <button onclick="showSection('searchSection')" class="px-3.5 py-2 rounded-xl font-semibold hover:bg-white/10 transition flex items-center gap-2 text-sm sm:text-base">
                        <i class="fas fa-search-location"></i> ፍላጎት ማቅረቢያ
                    </button>
                    
                    <div id="guestNav" class="flex items-center space-x-2 pl-2 border-l border-red-800">
                        <button onclick="showSection('loginSection')" class="px-3 py-2 font-semibold hover:text-yellow-300 transition text-sm sm:text-base">ግባ</button>
                        <button onclick="showSection('registerSection')" class="bg-gradient-to-r from-yellow-400 to-amber-400 hover:from-yellow-300 hover:to-amber-300 text-red-950 font-extrabold py-2 px-4 rounded-xl transition shadow-lg text-sm sm:text-base">ተመዝገብ</button>
                    </div>

                    <div id="userNav" class="hidden-section flex items-center space-x-3 pl-2 border-l border-red-800">
                        <span id="welcomeMessage" class="font-medium text-sm hidden lg:block bg-red-950/60 px-3.5 py-1.5 rounded-xl border border-red-800 text-yellow-200"></span>
                        <button onclick="showDashboard()" class="bg-white/10 hover:bg-white/20 px-3.5 py-2 rounded-xl transition font-semibold text-sm flex items-center gap-1.5">
                            <i class="fas fa-tachometer-alt text-yellow-400"></i> ዳሽቦርድ
                        </button>
                        <button onclick="logout()" class="bg-rose-700 hover:bg-rose-800 text-white font-bold py-2 px-3 rounded-xl transition text-sm shadow">ውጣ</button>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">

        <div id="homeSection" class="fade-in">
            <!-- Hero Banner -->
            <div class="relative bg-gradient-to-br from-red-950 via-red-900 to-rose-950 text-white rounded-3xl p-8 md:p-12 shadow-2xl overflow-hidden mb-12 border border-red-800/40">
                <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-yellow-500/10 rounded-full blur-3xl pointer-events-none"></div>
                <div class="relative z-10 max-w-2xl">
                    <span class="inline-flex items-center gap-1.5 bg-yellow-400/20 text-yellow-300 border border-yellow-400/40 text-xs font-bold px-3.5 py-1.5 rounded-full uppercase tracking-wider mb-4 shadow-sm">
                        <i class="fas fa-fire text-yellow-400"></i> አዲስ የተመዘገቡ የቅንጦት ቤቶች እና ቦታዎች
                    </span>
                    <h1 class="text-4xl md:text-5xl font-black tracking-tight mb-4 leading-tight">
                        የሕልምዎን ቤት ወይም የንግድ ቦታ <span class="text-yellow-400 underline decoration-yellow-400/50">ዛሬውኑ</span> ያግኙ!
                    </h1>
                    <p class="text-red-100/90 text-base md:text-lg mb-8 leading-relaxed">
                        በአዲስ አበባ እና ዙሪያዋ ከታማኝ ደላሎች እና ባለቤቶች የቀረቡ ከ16 በላይ የተመረጡ ዘመናዊ መኖሪያ ቤቶች፣ አፓርታማዎች እና ሰፊ ባዶ ቦታዎች በከፍተኛ ጥራት።
                    </p>
                    <div class="flex flex-wrap gap-4">
                        <button onclick="showSection('searchSection')" class="bg-gradient-to-r from-yellow-400 to-amber-400 hover:from-yellow-300 hover:to-amber-300 text-red-950 font-extrabold px-8 py-3.5 rounded-2xl shadow-xl transition flex items-center gap-2 transform hover:-translate-y-0.5">
                            <i class="fas fa-search-location"></i> የሚፈልጉትን ቦታ ወይም ቤት ይፃፉ
                        </button>
                        <a href="#propertiesGrid" class="bg-white/10 hover:bg-white/20 border border-white/20 text-white font-bold px-6 py-3.5 rounded-2xl transition flex items-center gap-2 backdrop-blur-sm">
                            <i class="fas fa-images"></i> ሁሉንም ቤቶች ይመልከቱ
                        </a>
                    </div>
                </div>
            </div>

            <!-- Filter Category Tabs -->
            <div class="flex flex-wrap items-center justify-between gap-4 mb-8 bg-white p-4 rounded-2xl shadow-sm border border-gray-200">
                <div class="flex flex-wrap gap-2">
                    <button onclick="filterProperties('all')" class="filter-btn active-filter bg-red-900 text-white px-5 py-2.5 rounded-xl text-sm font-bold shadow transition flex items-center gap-2">
                        <i class="fas fa-th-large"></i> ሁሉም (16)
                    </button>
                    <button onclick="filterProperties('መኖሪያ ቤት')" class="filter-btn bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2.5 rounded-xl text-sm font-semibold transition">
                        መኖሪያ ቤቶች (5)
                    </button>
                    <button onclick="filterProperties('አፓርታማ')" class="filter-btn bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2.5 rounded-xl text-sm font-semibold transition">
                        አፓርታማዎች (5)
                    </button>
                    <button onclick="filterProperties('ባዶ ቦታ')" class="filter-btn bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2.5 rounded-xl text-sm font-semibold transition">
                        ባዶ ቦታዎች (3)
                    </button>
                    <button onclick="filterProperties('የንግድ ቦታ')" class="filter-btn bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2.5 rounded-xl text-sm font-semibold transition">
                        የንግድ ቦታዎች (3)
                    </button>
                </div>
                <div class="text-sm font-semibold text-red-900 bg-red-50 px-4 py-2 rounded-xl border border-red-100 flex items-center gap-2">
                    <i class="fas fa-shield-check text-red-700"></i> የተረጋገጡ ትክክለኛ ንብረቶች
                </div>
            </div>

            <!-- Properties Grid -->
            <div id="propertiesGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Populated dynamically -->
            </div>
        </div>

        <div id="searchSection" class="hidden-section fade-in max-w-4xl mx-auto py-4">
            <div class="bg-white rounded-3xl shadow-2xl border border-red-100 overflow-hidden">
                <div class="bg-gradient-to-r from-red-900 via-rose-900 to-red-950 p-8 md:p-10 text-white text-center">
                    <div class="w-16 h-16 bg-gradient-to-br from-yellow-400 to-amber-500 mx-auto rounded-2xl flex items-center justify-center mb-4 shadow-xl text-red-950 font-bold border border-yellow-300">
                        <i class="fas fa-search-location text-3xl"></i>
                    </div>
                    <h2 class="text-3xl font-black mb-2">የሚፈልጉትን ቤት ወይም ቦታ በቀላሉ ያግኙ!</h2>
                    <p class="text-red-100 text-sm md:text-base max-w-xl mx-auto leading-relaxed">
                        የሚፈልጉትን የንብረት ዓይነት፣ አካባቢ እና በጀት እዚህ ይጻፉ። የተመዘገቡ ባለሙያ ደላሎች ወዲያውኑ አማራጮችን አቅርበው በስልክ ቁጥርዎ ወይም በኢሜልዎ ይደውሉልዎታል።
                    </p>
                </div>

                <div class="p-8 md:p-10">
                    <form onsubmit="handlePublicRequirementSubmit(event)" class="space-y-6">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">ሙሉ ስምዎ</label>
                                <input type="text" id="pubName" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition" placeholder="ምሳሌ፡ አበበ ከበደ" required>
                            </div>
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">ስልክ ቁጥር ወይም ኢሜል (ለደላሎች እንዲታይ)</label>
                                <input type="text" id="pubContact" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition" placeholder="ምሳሌ፡ 0911223344" required>
                            </div>
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">የንብረት ዓይነት</label>
                                <select id="pubType" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition">
                                    <option value="መኖሪያ ቤት">መኖሪያ ቤት (Villa / House)</option>
                                    <option value="አፓርታማ">አፓርታማ (Apartment)</option>
                                    <option value="ባዶ ቦታ">ባዶ ቦታ (Land / Plot)</option>
                                    <option value="የንግድ ቦታ">የንግድ ቦታ (Commercial / Shop)</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">ግዢ ወይስ ኪራይ?</label>
                                <select id="pubAction" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition">
                                    <option value="ግዢ">ለመግዛት (Purchase)</option>
                                    <option value="ኪራይ">ለመከራየት (Rent)</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">የሚፈልጉበት አካባቢ</label>
                                <input type="text" id="pubLocation" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition" placeholder="ምሳሌ፡ ቦሌ፣ ሲኤምሲ፣ ሳሪስ፣ ፒያሳ..." required>
                            </div>
                            <div>
                                <label class="block text-gray-800 font-bold text-sm mb-2">የበጀት መጠን (በብር)</label>
                                <input type="text" id="pubBudget" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition" placeholder="ምሳሌ፡ 8,000,000 ብር" required>
                            </div>
                        </div>
                        <div>
                            <label class="block text-gray-800 font-bold text-sm mb-2">ተጨማሪ ዝርዝር ማብራሪያ (የክፍል ብዛት፣ ስፋት፣ ወዘተ)</label>
                            <textarea id="pubDetails" rows="4" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3.5 focus:ring-2 focus:ring-red-800 focus:outline-none transition" placeholder="ለምሳሌ፡ 3 መኝታ ቤት ያለው፣ መኪና ማቆሚያ እና የውሃ ታንከር የተሟላለት ቢሆን..." required></textarea>
                        </div>
                        <button type="submit" class="w-full bg-gradient-to-r from-red-900 to-rose-900 hover:from-red-950 hover:to-rose-950 text-white font-extrabold py-4 rounded-2xl shadow-xl transition flex items-center justify-center gap-2 text-lg">
                            <i class="fas fa-paper-plane text-yellow-400"></i> ፍላጎትዎን ለደላሎች ያስተላልፉ
                        </button>
                    </form>
                </div>
            </div>
        </div>

        <div id="loginSection" class="hidden-section fade-in max-w-md mx-auto py-12">
            <div class="bg-white p-8 md:p-10 rounded-3xl shadow-2xl border-t-8 border-red-900">
                <div class="text-center mb-8">
                    <div class="w-16 h-16 bg-red-100 text-red-900 rounded-2xl mx-auto flex items-center justify-center text-2xl font-bold mb-3 shadow-inner">
                        <i class="fas fa-lock"></i>
                    </div>
                    <h2 class="text-2xl font-black text-gray-900">ወደ አካውንትዎ ይግቡ</h2>
                    <p class="text-sm text-gray-500 mt-1">et.brokers መድረክን ይቀላቀሉ</p>
                </div>
                <form id="loginForm" onsubmit="handleLogin(event)" class="space-y-5">
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">ስልክ ቁጥር ወይም ኢሜል</label>
                        <input class="w-full bg-gray-50 border border-gray-300 rounded-2xl py-3.5 px-4 text-gray-700 focus:ring-2 focus:ring-red-900 focus:outline-none" id="loginEmail" type="text" placeholder="ምሳሌ፡ 0911223344" required>
                    </div>
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">የይለፍ ቃል (Password)</label>
                        <input class="w-full bg-gray-50 border border-gray-300 rounded-2xl py-3.5 px-4 text-gray-700 focus:ring-2 focus:ring-red-900 focus:outline-none" id="loginPassword" type="password" placeholder="••••••••" required>
                    </div>
                    <button class="w-full bg-red-900 hover:bg-red-950 text-white font-bold py-3.5 rounded-2xl shadow-lg transition text-base" type="submit">
                        ግባ
                    </button>
                    <p class="text-center text-sm text-gray-600 pt-2">
                        አካውንት የለዎትም? <a href="#" onclick="showSection('registerSection')" class="text-red-900 font-bold hover:underline">እዚህ ይመዝገቡ</a>
                    </p>
                </form>
            </div>
        </div>

        <div id="registerSection" class="hidden-section fade-in max-w-lg mx-auto py-8">
            <div class="bg-white p-8 md:p-10 rounded-3xl shadow-2xl border-t-8 border-yellow-500">
                <div class="text-center mb-8">
                    <div class="w-16 h-16 bg-yellow-100 text-yellow-800 rounded-2xl mx-auto flex items-center justify-center text-2xl font-bold mb-3 shadow-inner">
                        <i class="fas fa-user-plus"></i>
                    </div>
                    <h2 class="text-2xl font-black text-gray-900">አዲስ አካውንት ይፍጠሩ</h2>
                    <p class="text-sm text-gray-500 mt-1">እንደ ገዢ ወይም እንደ ደላላ ይመዝገቡ</p>
                </div>
                <form id="registerForm" onsubmit="handleRegister(event)" class="space-y-5">
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">የተጠቃሚ ዓይነት</label>
                        <div class="grid grid-cols-2 gap-4">
                            <label class="flex items-center justify-center p-3.5 rounded-2xl border-2 border-red-200 bg-red-50/50 cursor-pointer hover:bg-red-100 transition">
                                <input type="radio" name="userType" value="buyer" class="text-red-900 focus:ring-red-800" checked>
                                <span class="ml-2 font-bold text-gray-800 text-sm">ገዢ / ተከራይ</span>
                            </label>
                            <label class="flex items-center justify-center p-3.5 rounded-2xl border-2 border-yellow-200 bg-yellow-50/50 cursor-pointer hover:bg-yellow-100 transition">
                                <input type="radio" name="userType" value="broker" class="text-red-900 focus:ring-red-800">
                                <span class="ml-2 font-bold text-gray-800 text-sm">ደላላ / አቅራቢ</span>
                            </label>
                        </div>
                    </div>
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">ሙሉ ስም</label>
                        <input class="w-full bg-gray-50 border border-gray-300 rounded-2xl py-3.5 px-4 text-gray-700 focus:ring-2 focus:ring-red-900 focus:outline-none" id="regName" type="text" placeholder="አበበ ከበደ" required>
                    </div>
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">ስልክ ቁጥር ወይም ኢሜል</label>
                        <input class="w-full bg-gray-50 border border-gray-300 rounded-2xl py-3.5 px-4 text-gray-700 focus:ring-2 focus:ring-red-900 focus:outline-none" id="regContact" type="text" placeholder="0911..." required>
                    </div>
                    <div>
                        <label class="block text-gray-700 text-sm font-bold mb-2">የይለፍ ቃል (Password)</label>
                        <input class="w-full bg-gray-50 border border-gray-300 rounded-2xl py-3.5 px-4 text-gray-700 focus:ring-2 focus:ring-red-900 focus:outline-none" id="regPassword" type="password" placeholder="••••••••" required>
                    </div>
                    <button class="w-full bg-gradient-to-r from-yellow-400 to-amber-400 hover:from-yellow-300 hover:to-amber-300 text-red-950 font-extrabold py-4 rounded-2xl shadow-lg transition text-base" type="submit">
                        ተመዝገብ
                    </button>
                </form>
            </div>
        </div>

        <div id="buyerDashboard" class="hidden-section fade-in">
            <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center mb-8 border-b pb-4 gap-4">
                <div>
                    <h2 class="text-3xl font-black text-gray-900">የገዢ ዳሽቦርድ</h2>
                    <p class="text-gray-600 text-sm">ያቀረቧቸው ጥያቄዎች እና ከደላሎች የተሰጡ የተረጋገጡ ምላሾች</p>
                </div>
                <button onclick="showSection('searchSection')" class="bg-red-900 hover:bg-red-950 text-white font-bold py-3 px-5 rounded-2xl shadow transition text-sm flex items-center gap-2">
                    <i class="fas fa-plus"></i> አዲስ ጥያቄ ጻፍ
                </button>
            </div>
            <div id="buyerRequestsList" class="grid grid-cols-1 md:grid-cols-2 gap-6"></div>
        </div>

        <div id="brokerDashboard" class="hidden-section fade-in">
            <div class="mb-8 border-b pb-4">
                <h2 class="text-3xl font-black text-gray-900">የደላላ ዳሽቦርድ (የገዢዎች ማርኬት ቦርድ)</h2>
                <p class="text-gray-600 text-sm">ገዢዎች የለጠፏቸውን ፍላጎቶች ተመልክተው ተስማሚ ቤት ወይም ቦታ ያቅርቡላቸው።</p>
            </div>
            <div id="marketBoardList" class="space-y-4"></div>
        </div>

    </main>

    <div id="propertyModal" class="fixed inset-0 bg-black/70 backdrop-blur-sm hidden flex items-center justify-center z-50 p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full max-h-[90vh] overflow-y-auto shadow-2xl relative animate-in fade-in zoom-in duration-200">
            <button onclick="closePropertyModal()" class="absolute top-4 right-4 bg-black/60 hover:bg-black text-white w-10 h-10 rounded-full flex items-center justify-center transition z-10 shadow-lg">
                <i class="fas fa-times"></i>
            </button>
            <div id="modalContent"></div>
        </div>
    </div>

    <div id="brokerResponseModal" class="fixed inset-0 bg-black/70 backdrop-blur-sm hidden flex items-center justify-center z-50 p-4">
        <div class="bg-white rounded-3xl max-w-lg w-full p-8 shadow-2xl relative">
            <h3 class="text-2xl font-black text-gray-900 mb-2">ለገዢው ያለዎትን ንብረት ያቅርቡ</h3>
            <p id="respondingToInfo" class="text-xs text-red-900 bg-red-50 p-3.5 rounded-2xl mb-6 font-semibold border border-red-100"></p>
            <form onsubmit="handleBrokerResponseSubmit(event)" class="space-y-4">
                <input type="hidden" id="replyToReqId">
                <div>
                    <label class="block text-gray-700 font-bold text-sm mb-1.5">የቤቱ/ቦታው ርዕስ (Title)</label>
                    <input type="text" id="propTitle" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3 focus:ring-2 focus:ring-red-900 focus:outline-none" placeholder="ምሳሌ፡ ቆንጆ G+2 ቪላ በቦሌ" required>
                </div>
                <div>
                    <label class="block text-gray-700 font-bold text-sm mb-1.5">ዋጋ (በብር)</label>
                    <input type="text" id="propPrice" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3 focus:ring-2 focus:ring-red-900 focus:outline-none" placeholder="ምሳሌ፡ 25,000,000 ብር" required>
                </div>
                <div>
                    <label class="block text-gray-700 font-bold text-sm mb-1.5">ዝርዝር መግለጫ</label>
                    <textarea id="propDetails" rows="3" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3 focus:ring-2 focus:ring-red-900 focus:outline-none" placeholder="የካሬ ስፋት፣ የክፍሎች ብዛት..." required></textarea>
                </div>
                <div>
                    <label class="block text-gray-700 font-bold text-sm mb-1.5">ስልክ ቁጥርዎ</label>
                    <input type="text" id="propContact" class="w-full bg-gray-50 border border-gray-300 rounded-2xl px-4 py-3 focus:ring-2 focus:ring-red-900 focus:outline-none" required>
                </div>
                <div class="flex justify-end space-x-3 pt-4">
                    <button type="button" onclick="closeModal('brokerResponseModal')" class="px-5 py-3 rounded-2xl bg-gray-100 hover:bg-gray-200 text-gray-700 font-bold transition">ይቅር</button>
                    <button type="submit" class="px-6 py-3 rounded-2xl bg-red-900 hover:bg-red-950 text-white font-bold shadow-lg transition">ላክ</button>
                </div>
            </form>
        </div>
    </div>

    <footer class="bg-gray-950 text-white py-12 mt-auto border-t border-gray-900">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <div class="flex items-center justify-center space-x-3 mb-4">
                <div class="w-10 h-10 bg-gradient-to-br from-yellow-400 to-amber-500 rounded-xl flex items-center justify-center text-red-950 font-bold shadow-lg">
                    <i class="fas fa-city"></i>
                </div>
                <span class="font-extrabold text-2xl tracking-tight">et<span class="text-yellow-400">.</span>brokers</span>
            </div>
            <p class="text-gray-400 text-sm mb-6 max-w-md mx-auto">በኢትዮጵያ ውስጥ ያሉ የሪል ስቴት እና የቦታ ግብይቶችን በዘመናዊ መንገድ ከታማኝ ደላሎች ጋር የሚያገናኝ መድረክ።</p>
            <div class="flex justify-center space-x-6 mb-8 text-red-400">
                <a href="#" class="hover:text-yellow-400 transition bg-white/5 p-3 rounded-xl border border-white/10"><i class="fab fa-telegram fa-lg"></i></a>
                <a href="#" class="hover:text-yellow-400 transition bg-white/5 p-3 rounded-xl border border-white/10"><i class="fab fa-facebook fa-lg"></i></a>
                <a href="#" class="hover:text-yellow-400 transition bg-white/5 p-3 rounded-xl border border-white/10"><i class="fab fa-tiktok fa-lg"></i></a>
                <a href="#" class="hover:text-yellow-400 transition bg-white/5 p-3 rounded-xl border border-white/10"><i class="fab fa-instagram fa-lg"></i></a>
            </div>
            <p class="text-xs text-gray-500">&copy; 2026 et.brokers. መብቱ በህግ የተጠበቀ ነው።</p>
        </div>
    </footer>

    <script>
        // 16 Real Estate Properties with high resolution imagery and descriptions
        const properties = [
            {
                id: 1,
                title: "ሉላዊ ዘመናዊ G+2 ቪላ በቦሌ አትላስ",
                category: "መኖሪያ ቤት",
                price: "38,000,000 ብር",
                location: "ቦሌ አትላስ፣ አዲስ አበባ",
                bedrooms: 5,
                bathrooms: 6,
                area: "350 ካሬ ሜትር",
                broker: "ዮናስ ደላላ (0911223344)",
                image: "https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?auto=format&fit=crop&w=800&q=80",
                description: "በጣም ዘመናዊ አጨራረስ ያለው፣ ሰፊ የመኪና ማቆሚያ (ለ4 መኪና)፣ የሰራተኛ ክፍል እና ዘመናዊ የኩሽና ዕቃዎች የተሟሉለት ውብ ቪላ።"
            },
            {
                id: 2,
                title: "የቅንጦት 3 መኝታ አፓርታማ በካዛንቺስ",
                category: "አፓርታማ",
                price: "16,500,000 ብር",
                location: "ካዛንቺስ፣ አዲስ አበባ",
                bedrooms: 3,
                bathrooms: 2,
                area: "160 ካሬ ሜትር",
                broker: "ሳራ ሪልስቴት (0922334455)",
                image: "https://images.unsplash.com/photo-1545324418-cc1a3fa10c00?auto=format&fit=crop&w=800&q=80",
                description: "ሊፍት (Elevator)፣ የጀነሬተር አገልግሎት፣ 24/7 የጸጥታ ጥበቃ እና ውብ ከንቲባ እይታ (City View) ያለው የላይኛው ፎቅ አፓርታማ።"
            },
            {
                id: 3,
                title: "ለኢንቨስትመንት የሚሆን ሰፊ ባዶ ቦታ በሰሚት",
                category: "ባዶ ቦታ",
                price: "22,000,000 ብር",
                location: "ሰሚት ሚካኤል፣ አዲስ አበባ",
                bedrooms: 0,
                bathrooms: 0,
                area: "500 ካሬ ሜትር",
                broker: "አማን የቦታ አላባ (0933445566)",
                image: "https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&w=800&q=80",
                description: "አስፋልት ንጣፍ ጋር የቀረበ፣ ለህንፃ ግንባታ ወይም ለድርጅት ዋና መሥሪያ ቤት የሚሆን ምቹ ማዕዘን (Corner Plot) ቦታ።"
            },
            {
                id: 4,
                title: "ለቢሮ አገልግሎት የሚሆን ዘመናዊ ሕንፃ ፎቅ",
                category: "የንግድ ቦታ",
                price: "75,000 ብር በወር",
                location: "ሜክሲኮ፣ አዲስ አበባ",
                bedrooms: 0,
                bathrooms: 4,
                area: "220 ካሬ ሜትር",
                broker: "ከድር ደላላ (0944556677)",
                image: "https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&w=800&q=80",
                description: "በዋናው መንገድ ላይ የሚገኝ፣ ለባንክ ቅርንጫፍ ወይም ለትልቅ ቢሮዎች የሚሆን ሙሉ ፎቅ ፓርኪንግ ያለው።"
            },
            {
                id: 5,
                title: "ባህላዊ እና ዘመናዊ የተዋሃደ ቪላ በሐያአንድ",
                category: "መኖሪያ ቤት",
                price: "29,000,000 ብር",
                location: "አያአንድ ዞን 2፣ አዲስ አበባ",
                bedrooms: 4,
                bathrooms: 4,
                area: "300 ካሬ ሜትር",
                broker: "መአዛ ብሮከር (0955667788)",
                image: "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?auto=format&fit=crop&w=800&q=80",
                description: "ጸጥታ የሰፈነበት ሰፈር ውስጥ የሚገኝ፣ አትክልት ማልማያ ቦታ ያለው እና በከፍተኛ ጥራት የተገነባ መኖሪያ ቤት።"
            },
            {
                id: 6,
                title: "ለኪራይ የቀረበ 2 መኝታ አፓርታማ በጀርመን ስድስት",
                category: "አፓርታማ",
                price: "35,000 ብር በወር",
                location: "ጀርመን ስድስት፣ አዲስ አበባ",
                bedrooms: 2,
                bathrooms: 2,
                area: "110 ካሬ ሜትር",
                broker: "ዳዊት ንብረት (0966778899)",
                image: "https://images.unsplash.com/photo-1502672260266-1c1ef2d93688?auto=format&fit=crop&w=800&q=80",
                description: "ሙሉ በሙሉ በቤት ዕቃዎች የተሟላ (Furnished)፣ ኢንተርኔት እና የኬብል ቴሌቪዥን የተዘረጋለት።"
            },
            {
                id: 7,
                title: "ስትራቴጂካዊ ቦታ ላይ የሚገኝ የንግድ ሱቅ",
                category: "የንግድ ቦታ",
                price: "12,000,000 ብር",
                location: "ፒያሳ፣ አዲስ አበባ",
                bedrooms: 0,
                bathrooms: 1,
                area: "85 ካሬ ሜትር",
                broker: "ብርሃኑ ደላላ (0977889900)",
                image: "https://images.unsplash.com/photo-1441986300917-64674bd600d8?auto=format&fit=crop&w=800&q=80",
                description: "ሰው ዝውውር ባለበት ከፍተኛ የንግድ ማዕከል ውስጥ የሚገኝ ሰፊ ሱቅ።"
            },
            {
                id: 8,
                title: "ሰፊ G+1 ቤተሰባዊ መኖሪያ ቤት በሲኤምሲ",
                category: "መኖሪያ ቤት",
                price: "24,500,000 ብር",
                location: "ሲኤምሲ ሚካኤል፣ አዲስ አበባ",
                bedrooms: 4,
                bathrooms: 3,
                area: "270 ካሬ ሜትር",
                broker: "ኤፍሬም የቤት ទីផ្សារ (0988990011)",
                image: "https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=800&q=80",
                description: "ለቤተሰብ ምቹ የሆነ ሰፊ ግቢ፣ ቋሚ የውሃ ማጠራቀሚያ እና ጥራት ያለው የእንጨት ስራዎች ያሉት።"
            },
            {
                id: 9,
                title: "ለቪላ ግንባታ የሚሆን ቦታ በለቡ",
                category: "ባዶ ቦታ",
                price: "14,000,000 ብር",
                location: "ለቡ መብራት ኃይል፣ አዲስ አበባ",
                bedrooms: 0,
                bathrooms: 0,
                area: "400 ካሬ ሜትር",
                broker: "ዮሴፍ ቦታ አገናኝ (0999001122)",
                image: "https://images.unsplash.com/photo-1524813686514-a57563d77840?auto=format&fit=crop&w=800&q=80",
                description: "ቀድሞ የተጠናቀቀ ሰነድ (Title Deed) ያለው፣ ለመኖሪያ ቤት ግንባታ ዝግጁ የሆነ ቦታ።"
            },
            {
                id: 10,
                title: "አዲስ የተገነባ 1 መኝታ ስቱዲዮ አፓርታማ",
                category: "አፓርታማ",
                price: "18,000 ብር በወር",
                location: "ቦሌ ቦርንሆል፣ አዲስ አበባ",
                bedrooms: 1,
                bathrooms: 1,
                area: "55 ካሬ ሜትር",
                broker: "ሔለን ደላላ (0912345678)",
                image: "https://images.unsplash.com/photo-1536376072261-38c75010e6c9?auto=format&fit=crop&w=800&q=80",
                description: "ለነጠላ ሰራተኞች ወይም ጥንዶች የሚሆን፣ ዘመናዊ የወጥ ቤት ዕቃዎች እና ፏፏቴ ያለው አፓርታማ።"
            },
            {
                id: 11,
                title: "ታላቅ ሪል ስቴት ቪላ በኮተቤ",
                category: "መኖሪያ ቤት",
                price: "31,000,000 ብር",
                location: "ኮተቤ ዩኒቨርሲቲ አካባቢ",
                bedrooms: 5,
                bathrooms: 5,
                area: "320 ካሬ ሜትር",
                broker: "አስራት ብሮከር (0923456789)",
                image: "https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?auto=format&fit=crop&w=800&q=80",
                description: "በተዘጋ የሪል ስቴት ማህበረሰብ ውስጥ የሚገኝ፣ የራሱ የመዋኛ ገንዳ እና የልጆች መጫወቻ ቦታ ያለው።"
            },
            {
                id: 12,
                title: "ለሱፐርማርኬት የሚሆን ሰፊ የንግድ ቦታ",
                category: "የንግድ ቦታ",
                price: "90,000 ብር በወር",
                location: "ሳሪስ አቦ፣ አዲስ አበባ",
                bedrooms: 0,
                bathrooms: 2,
                area: "300 ካሬ ሜትር",
                broker: "ጌታቸው መሬት (0934567890)",
                image: "https://images.unsplash.com/photo-1555396273-367ea4eb4db5?auto=format&fit=crop&w=800&q=80",
                description: "በመኖሪያ አፓርታማዎች መሃል የሚገኝ፣ ለንግድ ስራ ከፍተኛ እንቅስቃሴ የሚታይበት ሰፊ ቦታ።"
            },
            {
                id: 13,
                title: "ውብ ባለ 4 መኝታ አፓርታማ በበለስ",
                category: "አፓርታማ",
                price: "21,000,000 ብር",
                location: "በለስ ሪል ስቴት፣ አዲስ አበባ",
                bedrooms: 4,
                bathrooms: 3,
                area: "190 ካሬ ሜትር",
                broker: "ተስፋዬ ደላላ (0945678901)",
                image: "https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?auto=format&fit=crop&w=800&q=80",
                description: "ምርጥ ጥራት ባላቸው የጣሊያን ሸክሞች የተሰራ፣ ሰፊ በረንዳ እና የቁም ሳንቲሞች ያሉት።"
            },
            {
                id: 14,
                title: "ለፋብሪካ ወይም መጋዘን የሚሆን ቦታ በቃሊቲ",
                category: "ባዶ ቦታ",
                price: "45,000,000 ብር",
                location: "ቃሊቲ ኢንዱስትሪ ዞን",
                bedrooms: 0,
                bathrooms: 0,
                area: "1200 ካሬ ሜትር",
                broker: "መንግስቱ አክሲዮን (0956789012)",
                image: "https://images.unsplash.com/photo-1578575437130-527eed3abbec?auto=format&fit=crop&w=800&q=80",
                description: "ከባድ መኪናዎች መግባት የሚያስችላቸው ሰፊ መንገዶች ያሉት እና ሃይቮልቴጅ ኤሌክትሪክ ያለው ቦታ።"
            },
            {
                id: 15,
                title: "ባለ 3 መኝታ መኖሪያ ቤት በኢገር",
                category: "መኖሪያ ቤት",
                price: "19,500,000 ብር",
                location: "ኢገር፣ አዲስ አበባ",
                bedrooms: 3,
                bathrooms: 2,
                area: "210 ካሬ ሜትር",
                broker: "ፍሬህይወት ደላላ (0967890123)",
                image: "https://images.unsplash.com/photo-1583608205776-bfd35f0d9f83?auto=format&fit=crop&w=800&q=80",
                description: "በተመጣጣኝ ዋጋ የቀረበ፣ ጥራቱን የጠበቀ እና ወዲያውኑ መግባት የሚቻልበት ዝግጁ ቤት።"
            },
            {
                id: 16,
                title: "የቅንጦት ፔንትሃውስ አፓርታማ ቦሌ መንገድ",
                category: "አፓርታማ",
                price: "42,000,000 ብር",
                location: "ቦሌ ማተሚያ ቤት ፊት ለፊት",
                bedrooms: 4,
                bathrooms: 5,
                area: "340 ካሬ ሜትር",
                broker: "ናቲ ሪልስቴት (0978901234)",
                image: "https://images.unsplash.com/photo-1513694203232-719a280e022f?auto=format&fit=crop&w=800&q=80",
                description: "የመጨረሻው ፎቅ ላይ የሚገኝ፣ ሰፊ ቴራስ እና መላውን ከተማ የሚቆጣጠር ውብ እይታ ያለው ልዩ ፔንትሃውስ።"
            }
        ];

        let currentUser = null;
        let users = [];
        let requirements = [
            {
                id: 101,
                buyerName: "አብይ ሰለሞን",
                contact: "0911000000",
                type: "መኖሪያ ቤት",
                action: "ግዢ",
                location: "ቦሌ ወይም ሲኤምሲ",
                budget: "25,000,000 - 35,000,000 ብር",
                details: "ቢያንስ 4 መኝታ ቤት ያለው፣ መኪና ማቆሚያ ያለው ቪላ እፈልጋለሁ።",
                date: "2026-10-01",
                responses: [
                    {
                        brokerName: "ዮናስ ደላላ",
                        title: "ሉላዊ ዘመናዊ G+2 ቪላ በቦሌ አትላስ",
                        price: "38,000,000 ብር",
                        details: "በጣም ዘመናዊ አጨራረስ ያለው፣ ሰፊ የመኪና ማቆሚያ (ለ4 መኪና)።",
                        contact: "0911223344"
                    }
                ]
            }
        ];

        // Section Navigation Manager
        const sections = ['homeSection', 'searchSection', 'loginSection', 'registerSection', 'buyerDashboard', 'brokerDashboard'];

        function showSection(sectionId) {
            sections.forEach(id => {
                const el = document.getElementById(id);
                if (el) el.style.display = 'none';
            });
            const target = document.getElementById(sectionId);
            if (target) {
                target.style.display = 'block';
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.add('hidden');
        }

        // Render Property Cards on Home Page
        function renderProperties(listToRender) {
            const grid = document.getElementById('propertiesGrid');
            if (!grid) return;
            grid.innerHTML = '';

            listToRender.forEach(p => {
                const card = `
                    <div class="bg-white rounded-3xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-300 border border-gray-100 flex flex-col group">
                        <div class="relative h-64 overflow-hidden bg-gray-200">
                            <img src="${p.image}" alt="${p.title}" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" onerror="this.src='https://placehold.co/600x400/991b1b/ffffff?text=et.brokers'">
                            <span class="absolute top-3 left-3 bg-red-900 text-white text-xs font-bold px-3.5 py-1.5 rounded-full shadow-md">
                                ${p.category}
                            </span>
                            <span class="absolute bottom-3 right-3 bg-black/75 backdrop-blur-md text-yellow-300 text-sm font-black px-3.5 py-1.5 rounded-xl shadow-lg">
                                ${p.price}
                            </span>
                        </div>
                        <div class="p-6 flex flex-col flex-grow">
                            <h3 class="font-extrabold text-xl text-gray-900 mb-2 group-hover:text-red-900 transition">${p.title}</h3>
                            <p class="text-gray-500 text-sm mb-4 flex items-center">
                                <i class="fas fa-map-marker-alt text-red-800 mr-2"></i> ${p.location}
                            </p>
                            <div class="grid grid-cols-3 gap-2 py-3 border-y border-gray-100 text-center text-xs text-gray-600 mb-4 bg-gray-50/80 rounded-2xl">
                                <div><strong class="block text-gray-900 text-sm">${p.bedrooms}</strong> መኝታ</div>
                                <div><strong class="block text-gray-900 text-sm">${p.bathrooms}</strong> መታጠቢያ</div>
                                <div><strong class="block text-gray-900 text-sm">${p.area}</strong> ስፋት</div>
                            </div>
                            <p class="text-gray-600 text-sm mb-6 line-clamp-2 leading-relaxed">${p.description}</p>
                            <div class="mt-auto flex items-center justify-between pt-3 border-t border-gray-100">
                                <span class="text-xs text-gray-500 font-semibold truncate max-w-[140px]"><i class="fas fa-user-tie text-red-800 mr-1"></i> ${p.broker.split('(')[0]}</span>
                                <button onclick="openPropertyModal(${p.id})" class="bg-red-900/10 hover:bg-red-900 hover:text-white text-red-900 font-bold px-4 py-2.5 rounded-xl text-xs transition whitespace-nowrap">
                                    ሙሉ መረጃ ይመልከቱ
                                </button>
                            </div>
                        </div>
                    </div>
                `;
                grid.innerHTML += card;
            });
        }

        function filterProperties(category) {
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.className = "filter-btn bg-gray-100 hover:bg-gray-200 text-gray-700 px-4 py-2.5 rounded-xl text-sm font-semibold transition";
            });
            event.currentTarget.className = "filter-btn bg-red-900 text-white px-5 py-2.5 rounded-xl text-sm font-bold shadow transition flex items-center gap-2";

            if (category === 'all') {
                renderProperties(properties);
            } else {
                const filtered = properties.filter(p => p.category === category);
                renderProperties(filtered);
            }
        }

        // Detailed Property Modal
        function openPropertyModal(id) {
            const p = properties.find(item => item.id === id);
            if (!p) return;

            const modalContent = document.getElementById('modalContent');
            modalContent.innerHTML = `
                <div class="relative h-72 sm:h-80">
                    <img src="${p.image}" class="w-full h-full object-cover" onerror="this.src='https://placehold.co/800x500/991b1b/ffffff?text=et.brokers'">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent flex items-end p-6">
                        <div>
                            <span class="bg-yellow-400 text-red-950 font-bold text-xs px-3 py-1 rounded-full uppercase">${p.category}</span>
                            <h2 class="text-2xl sm:text-3xl font-black text-white mt-2">${p.title}</h2>
                            <p class="text-red-200 text-sm mt-1"><i class="fas fa-map-marker-alt mr-1"></i> ${p.location}</p>
                        </div>
                    </div>
                </div>
                <div class="p-6 sm:p-8 space-y-6">
                    <div class="flex flex-wrap items-center justify-between bg-red-50 p-4 rounded-2xl border border-red-100">
                        <div>
                            <span class="text-xs text-gray-500 block uppercase font-bold">የተጠየቀው ዋጋ</span>
                            <span class="text-2xl font-black text-red-900">${p.price}</span>
                        </div>
                        <div class="flex gap-3 text-center">
                            <div class="bg-white px-4 py-2 rounded-xl shadow-sm">
                                <span class="text-xs text-gray-400 block">መኝታ</span>
                                <strong class="text-gray-900">${p.bedrooms}</strong>
                            </div>
                            <div class="bg-white px-4 py-2 rounded-xl shadow-sm">
                                <span class="text-xs text-gray-400 block">መታጠቢያ</span>
                                <strong class="text-gray-900">${p.bathrooms}</strong>
                            </div>
                            <div class="bg-white px-4 py-2 rounded-xl shadow-sm">
                                <span class="text-xs text-gray-400 block">ስፋት</span>
                                <strong class="text-gray-900">${p.area}</strong>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h4 class="font-bold text-gray-900 text-lg mb-2">ንብረቱን በተመለከተ</h4>
                        <p class="text-gray-600 leading-relaxed">${p.description}</p>
                    </div>
                    <div class="bg-gray-50 p-4 rounded-2xl border flex flex-col sm:flex-row items-center justify-between gap-4">
                        <div>
                            <span class="text-xs text-gray-500 block font-bold">ኃላፊ / ደላላ</span>
                            <span class="font-black text-gray-900 text-base"><i class="fas fa-phone-alt text-red-800 mr-2"></i> ${p.broker}</span>
                        </div>
                        <a href="tel:${p.broker.split('(')[1]?.replace(')', '') || ''}" class="w-full sm:w-auto bg-red-900 hover:bg-red-950 text-white font-bold px-6 py-3 rounded-xl shadow transition text-sm text-center">
                            አሁን ይደውሉ
                        </a>
                    </div>
                </div>
            `;
            document.getElementById('propertyModal').classList.remove('hidden');
        }

        function closePropertyModal() {
            document.getElementById('propertyModal').classList.add('hidden');
        }

        // Public Requirement Submission Handler
        function handlePublicRequirementSubmit(e) {
            e.preventDefault();
            const newReq = {
                id: Date.now(),
                buyerName: document.getElementById('pubName').value,
                contact: document.getElementById('pubContact').value,
                type: document.getElementById('pubType').value,
                action: document.getElementById('pubAction').value,
                location: document.getElementById('pubLocation').value,
                budget: document.getElementById('pubBudget').value,
                details: document.getElementById('pubDetails').value,
                date: new Date().toLocaleDateString('am-ET'),
                responses: []
            };

            requirements.unshift(newReq);
            e.target.reset();
            showToast("ፍላጎትዎ በተሳካ ሁኔታ ተመዝግቧል! ደላሎች አሁን ይመለከቱታል።");
            
            if (currentUser && currentUser.type === 'buyer') {
                showDashboard();
            } else {
                showSection('homeSection');
            }
        }

        function showToast(message) {
            const toast = document.createElement('div');
            toast.className = 'fixed bottom-6 right-6 bg-red-950 text-white px-6 py-4 rounded-2xl shadow-2xl z-50 fade-in flex items-center gap-3 border border-red-800';
            toast.innerHTML = `<i class="fas fa-check-circle text-yellow-400 text-xl"></i> <span class="font-bold text-sm">${message}</span>`;
            document.body.appendChild(toast);
            setTimeout(() => toast.remove(), 3500);
        }

        // Auth & Nav State
        function updateNav() {
            if (currentUser) {
                document.getElementById('guestNav').style.display = 'none';
                document.getElementById('userNav').style.display = 'flex';
                document.getElementById('welcomeMessage').innerText = `ሰላም, ${currentUser.name}`;
            } else {
                document.getElementById('guestNav').style.display = 'flex';
                document.getElementById('userNav').style.display = 'none';
            }
        }

        function handleRegister(e) {
            e.preventDefault();
            const type = document.querySelector('input[name="userType"]:checked').value;
            const name = document.getElementById('regName').value;
            const contact = document.getElementById('regContact').value;

            const newUser = { id: Date.now(), type, name, contact };
            users.push(newUser);
            currentUser = newUser;
            e.target.reset();
            showToast(`እንኳን ደህና መጡ ${name}! አካውንትዎ ተፈጥሯል።`);
            updateNav();
            showDashboard();
        }

        function handleLogin(e) {
            e.preventDefault();
            const contact = document.getElementById('loginEmail').value;
            let user = users.find(u => u.contact === contact);
            if (!user) {
                user = { id: Date.now(), type: contact.includes('broker') ? 'broker' : 'buyer', name: "ተጠቃሚ", contact };
            }
            currentUser = user;
            e.target.reset();
            showToast("በተሳካ ሁኔታ ገብተዋል!");
            updateNav();
            showDashboard();
        }

        function logout() {
            currentUser = null;
            updateNav();
            showSection('homeSection');
            showToast("ከአካውንትዎ ወጥተዋል");
        }

        function showDashboard() {
            if (!currentUser) return showSection('loginSection');
            if (currentUser.type === 'buyer') {
                renderBuyerDashboard();
                showSection('buyerDashboard');
            } else {
                renderBrokerDashboard();
                showSection('brokerDashboard');
            }
        }

        function renderBuyerDashboard() {
            const list = document.getElementById('buyerRequestsList');
            if (!list) return;
            list.innerHTML = '';

            if (requirements.length === 0) {
                list.innerHTML = `<p class="text-gray-500 italic col-span-2">እስካሁን ምንም ጥያቄ አላቀረቡም።</p>`;
                return;
            }

            requirements.forEach(req => {
                let responsesHtml = '';
                if (req.responses && req.responses.length > 0) {
                    responsesHtml = `
                        <div class="mt-4 pt-4 border-t border-gray-100">
                            <h4 class="font-bold text-red-900 mb-3 text-sm flex items-center gap-1.5">
                                <i class="fas fa-bell text-yellow-500"></i> ${req.responses.length} ደላሎች ምላሽ ሰጥተዋል!
                            </h4>
                            <div class="space-y-3">
                                ${req.responses.map(res => `
                                    <div class="bg-red-50/60 p-4 rounded-2xl border border-red-100">
                                        <div class="flex justify-between items-center font-bold text-gray-900 mb-1">
                                            <span>${res.title}</span>
                                            <span class="text-red-900 text-sm font-black">${res.price}</span>
                                        </div>
                                        <p class="text-xs text-gray-600 mb-2 leading-relaxed">${res.details}</p>
                                        <div class="text-xs font-bold text-gray-800 flex items-center gap-1.5">
                                            <i class="fas fa-phone-alt text-red-800"></i> ደላላ: ${res.brokerName} (${res.contact})
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        </div>
                    `;
                } else {
                    responsesHtml = `<p class="mt-4 pt-4 border-t border-gray-100 text-xs text-gray-500 italic"><i class="fas fa-clock mr-1"></i> ደላሎች ጥያቄዎን እያዩት ነው። ምላሽ ይጠብቁ...</p>`;
                }

                list.innerHTML += `
                    <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100 relative">
                        <span class="absolute top-6 right-6 bg-red-100 text-red-900 font-bold text-xs px-3 py-1 rounded-full">${req.action}</span>
                        <h3 class="font-extrabold text-lg text-gray-900 mb-1">${req.type} - ${req.location}</h3>
                        <p class="text-xs text-gray-500 mb-3">በጀት: <strong class="text-gray-800">${req.budget}</strong></p>
                        <p class="text-gray-600 text-sm bg-gray-50 p-3.5 rounded-2xl mb-3 leading-relaxed">${req.details}</p>
                        ${responsesHtml}
                    </div>
                `;
            });
        }

        function renderBrokerDashboard() {
            const list = document.getElementById('marketBoardList');
            if (!list) return;
            list.innerHTML = '';

            requirements.forEach(req => {
                list.innerHTML += `
                    <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100 flex flex-col md:flex-row justify-between items-start md:items-center gap-6">
                        <div class="space-y-1.5">
                            <div class="flex items-center gap-2">
                                <span class="bg-red-900 text-white text-xs font-bold px-2.5 py-1 rounded-lg">${req.action}</span>
                                <h3 class="font-extrabold text-lg text-gray-900">${req.type} በ ${req.location}</h3>
                            </div>
                            <p class="text-xs text-gray-500">ገዢ: <strong class="text-gray-800">${req.buyerName}</strong> | በጀት: <strong class="text-red-900">${req.budget}</strong> | ቀን: ${req.date}</p>
                            <p class="text-gray-600 text-sm bg-gray-50 p-3.5 rounded-2xl mt-2 leading-relaxed">"${req.details}"</p>
                        </div>
                        <button onclick="openRespondModal(${req.id})" class="w-full md:w-auto bg-gradient-to-r from-yellow-400 to-amber-400 hover:from-yellow-300 hover:to-amber-300 text-red-950 font-black px-6 py-3.5 rounded-2xl shadow transition text-sm flex items-center justify-center gap-2 whitespace-nowrap">
                            <i class="fas fa-reply"></i> ንብረት አቅርብ
                        </button>
                    </div>
                `;
            });
        }

        function openRespondModal(reqId) {
            const req = requirements.find(r => r.id === reqId);
            if (!req) return;
            document.getElementById('replyToReqId').value = reqId;
            document.getElementById('respondingToInfo').innerText = `ለገዢው (${req.buyerName}) - የሚፈልጉት: ${req.type} በ ${req.location} (${req.budget})`;
            if (currentUser && currentUser.contact) {
                document.getElementById('propContact').value = currentUser.contact;
            }
            document.getElementById('brokerResponseModal').classList.remove('hidden');
        }

        function handleBrokerResponseSubmit(e) {
            e.preventDefault();
            const reqId = parseInt(document.getElementById('replyToReqId').value);
            const req = requirements.find(r => r.id === reqId);
            if (req) {
                if (!req.responses) req.responses = [];
                req.responses.push({
                    brokerName: currentUser?.name || "ባለሙያ ደላላ",
                    title: document.getElementById('propTitle').value,
                    price: document.getElementById('propPrice').value,
                    details: document.getElementById('propDetails').value,
                    contact: document.getElementById('propContact').value
                });
                showToast("መረጃው ለገዢው በተሳካ ሁኔታ ተልኳል!");
            }
            e.target.reset();
            closeModal('brokerResponseModal');
            renderBrokerDashboard();
        }

        // Initialize App on Window Load
        window.onload = function() {
            renderProperties(properties);
            showSection('homeSection');
            updateNav();
        };
    </script>
</body>
</html>
```
