<template>
    <div class="min-h-screen bg-black relative overflow-hidden flex items-center justify-center">
        <!-- Background Pattern -->
        <div class="absolute inset-0 opacity-10">
            <div class="grid grid-cols-12 gap-4 transform rotate-12 scale-150">
                <div v-for="i in 144" :key="i"
                    class="w-8 h-8 border border-green-500 rounded flex items-center justify-center text-green-500 text-xs">
                    {{ patternIcons[(i - 1) % 10] }}
                </div>
            </div>
        </div>

        <!-- Main Card -->
        <div
            class="relative z-10 bg-gray-900 rounded-2xl py-8 px-4 w-full max-w-md mx-4 shadow-2xl border border-gray-800">

            <!-- Profile Circle -->
            <div class="flex justify-center mb-6">
                <div @click="redirectToTg"
                    class="cursor-pointer w-20 h-20 bg-black rounded-full border-2 border-white flex items-center justify-center">
                    <img src="/img1.jpeg" class="rounded-full" alt="">
                </div>
            </div>

            <!-- Title -->
            <h1 class="text-white text-2xl font-bold text-center mb-3 leading-tight">
                🏆 BANKNIFTY SNIPER BOT (FREE)
            </h1>

            <!-- Sub Text -->
            <p class="text-yellow-400 text-center text-sm mb-4 font-medium">
                👉 Join now before access closes
            </p>

            <!-- What You Get -->
            <div class="text-white text-sm mb-3 text-center">
                <span class="text-blue-400 font-semibold">👉 What You Get:</span>
            </div>

            <div class="space-y-2 text-white text-sm text-center">
                <div>✅ Clear Entry & Exit Points (Entry, Target, Stoploss)</div>
                <div>✅ No Guesswork – Fully System-Based Trading</div>
                
            </div>

            <!-- Important Warning -->
            <div class="bg-red-500/10 border border-red-500/30 rounded-lg p-3 mt-5 text-sm text-white text-center">
                ⚠️ <span class="font-semibold">IMPORTANT:</span> Don’t Miss This Step  
                <br /><br />
                Most users click the button but forget to tap <b>"JOIN"</b> inside Telegram  
                <br /><br />
                ❌ If you don’t tap JOIN, access will not be available  
                <br /><br />
                👉 Smart traders complete the final step and get instant access
            </div>

            <!-- CTA Text -->
            <p class="text-white text-center my-5 font-medium">
                👇 Click below to open Telegram
            </p>

            <!-- Join Button -->
            <div class="flex justify-center">
                <button @click="redirectToTg"
                    class="join-button relative bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-8 rounded-full transition-all duration-300 overflow-hidden transform hover:scale-105">
                    <span class="relative z-10">🔵 Open Telegram & Join Now</span>
                    <div
                        class="shine-overlay absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent transform -translate-x-full skew-x-12">
                    </div>
                </button>
            </div>

            <!-- Footer Note -->
            <p class="text-white/60 text-center text-xs mt-4">
                ⚠️ Telegram will open after clicking — make sure to tap <b>"JOIN"</b>
            </p>

            <!-- Disclaimer -->
            <div class="text-sm text-white/40 leading-tight mt-4 text-center">
                Disclaimer - Forex, CFDs, and leveraged trading instruments carry substantial risk. 
                The performance of this EA, including backtesting and forward testing, is not a guarantee of future profitability. 
                Market conditions can change at any time, affecting EA performance. 
                This product is provided for informational and educational purposes only and should not be considered financial or investment advice. 
                Users are solely responsible for their trading decisions and risk management. We are not liable for any losses incurred.
            </div>

        </div>
    </div>
</template>

<script setup>
const redirectToTg = () => {
    const params = new URLSearchParams(window.location.search)
    const campaign = params.get('utm_campaign')

    // let telegramLink = "https://t.me/+bLbJAx1la6YxZDE9"
    let telegramLink = "https://t.me/+CwLxvrS09nU5MzRl"
    

    if (campaign === "camp1") {
        telegramLink = "https://t.me/+CwLxvrS09nU5MzRl"
    } else if (campaign === "camp2") {
        telegramLink = "https://t.me/+GR9e4wp_zfwwYmY1"
    } else if (campaign === "camp3") {
        telegramLink = "https://t.me/+2qT3h40yT9FiM2I1"
    } else if (campaign === "camp4") {
        telegramLink = "https://t.me/+SjXso73_SZtlNjc9"
    }

    if (window.fbq) {
        window.fbq('track', 'Subscribe', {
            campaign: campaign || "default"
        })
    }

    window.open(telegramLink, '_blank')
}

const patternIcons = ['📊', '💰', '📈', '🎯', '⚡', '💹', '📋', '⏰', '🔔', '💎']
</script>

<style scoped>
@keyframes shine {
    0% {
        transform: translateX(-100%) skewX(-15deg);
    }

    100% {
        transform: translateX(200%) skewX(-15deg);
    }
}

.join-button:hover .shine-overlay {
    animation: shine 0.8s ease-in-out;
}

.join-button {
    position: relative;
    background: linear-gradient(45deg, #2563eb, #3b82f6);
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
}

.join-button:hover {
    box-shadow: 0 6px 20px rgba(37, 99, 235, 0.4);
    transform: scale(1.05) translateY(-1px);
}

.join-button::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
    animation: shine-continuous 3s infinite;
    z-index: 1;
}

@keyframes shine-continuous {
    0% {
        left: -100%;
    }

    50% {
        left: 100%;
    }

    100% {
        left: 100%;
    }
}

.bg-black {
    background: radial-gradient(ellipse at center, #1a1a2e 0%, #000000 70%);
}
</style>
