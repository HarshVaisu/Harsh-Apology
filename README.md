# Harsh-Apology
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Vaishnavi</title>
    <script src="https://cdn.tailwindcss.com">}
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Playfair+Display:wght@700&display=swap');
        .heart {
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-pink-50 to-red-50 min-h-screen flex items-center justify-center p-4">
    <div class="max-w-2xl bg-white rounded-2xl shadow-xl overflow-hidden">
        <div class="relative">
            <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/5e98e215-e849-4450-9bdd-bdf25a7706ef.png" alt="Tearful apology message with heart illustration" class="w-full h-48 object-cover"/>
            <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center">
                <h1 class="text-4xl md:text-5xl font-bold text-white font-serif italic tracking-wider drop-shadow-lg">For Vaishnavi</h1>
            </div>
        </div>
        
        <div class="p-8 md:p-10 relative" id="apologyMessage">
            <div class="text-center">
                <span class="heart text-6xl text-red-600 animate-pulse drop-shadow-md">❤️</span>
                <p class="mt-6 text-xl md:text-2xl text-gray-800 font-medium leading-relaxed tracking-wide" id="messageContent">
                    I AM SORRY VAISHNAVI<br>
                    I know Aap Hurt ho<br>
                    <span class="font-['Dancing+Script'] text-3xl text-red-600 block my-4">but I Didn't Mean to hurt you Kabhi Bhi ni</span>
                    Please Aap Mere Se Gusaa Na Ho...
                </p>
                <div class="mt-10 mb-6">
                    <span class="heart text-5xl text-red-400">♥</span>
                </div>
            </div>
            
            <div class="bg-pink-100 bg-opacity-50 p-4 rounded-lg border border-pink-200 mt-8 space-y-4">
                <div class="bg-white p-3 rounded-md">
                    <p class="text-sm text-gray-600 mb-1">Copy this link to share:</p>
                    <div class="flex items-center gap-2">
                        <input type="text" id="shareableLink" 
                            class="flex-1 border border-gray-300 rounded px-3 py-2 text-sm"
                            readonly 
                            value="Copy this link after hosting:" placeholder="URL will appear once hosted" />
                        <button class="copy-btn bg-blue-500 hover:bg-blue-600 text-white px-3 py-2 rounded text-sm">
                            Copy Link
                        </button>
                    </div>
                </div>
                <button 
                    onclick="shareOnWhatsApp()"
                    class="bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-6 rounded-lg w-full shadow-md transition-all duration-300 flex items-center justify-center gap-2"
                >
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                        <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-6.29-3.81a3.79 3.79 0 0 0 3.79 3.79 3.79 3.79 0 0 0 3.789-3.79 3.79 3.79 0 0 0-3.79-3.79 3.79 3.79 0 0 0-3.789 3.79m5.526-7.384a7.576 7.576 0 0 0-6.315-3.489 7.575 7.575 0 0 0-6.316 3.489 7.576 7.576 0 0 0 .16 8.162L3.3 17.998l4.286-1.126a7.6 7.6 0 0 0 3.58.895h.003a7.574 7.574 0 0 0 6.315-3.488A7.57 7.57 0 0 0 19 7.576a7.588 7.588 0 0 0-.894-3.577z"/>
                    </svg>
                    Share on WhatsApp
                </button>
            </div>
        </div>
    </div>

    <script>
        function copyLink() {
            const currentUrl = window.location.href;
            const linkInput = document.getElementById('shareableLink');
            linkInput.value = currentUrl; // Ensure URL is set first
            linkInput.select();
            
            try {
                navigator.clipboard.writeText(currentUrl).then(() => {
                    alert('Link copied to clipboard: ' + currentUrl);
                });
            } catch (err) {
                document.execCommand('copy');
                alert('Link copied!');
            }
        }

        function shareOnWhatsApp() {
            const pageUrl = window.location.href;
            const message = `I AM SORRY VAISHNAVI\nI know Aap Hurt ho\nbut I Didn't Mean to hurt you Kabhi Bhi ni\nPlease Aap Mere Se Gusaa Na Ho...\n\n${pageUrl}`;
            window.open(`https://api.whatsapp.com/send?text=${encodeURIComponent(message)}`, '_blank');
        }

        // Initialize immediately on page load
        document.addEventListener('DOMContentLoaded', function() {
            const currentUrl = window.location.href;
            const linkInput = document.getElementById('shareableLink');
            linkInput.value = currentUrl;
            
            // Set up copy button
            document.querySelector('.copy-btn').addEventListener('click', copyLink);
            
            // Display URL immediately
            if (window.location.href.includes('http')) {
                linkInput.value = window.location.href;
            } else {
                linkInput.value = "Please host this page to get a shareable link";
            }
        });
    }
    </script>
</body>
</html>

