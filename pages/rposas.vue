<template>
    <div class="min-h-screen bg-gray-50 text-gray-900 font-sans px-6 py-12">
        <div class="max-w-3xl mx-auto bg-white rounded-2xl shadow-xl p-8 space-y-12 border border-gray-300">

            <header class="text-center space-y-4">
                <img src="/public/rposas.jpg" alt="Profile"
                     class="w-24 h-24 rounded-full mx-auto ring-4 ring-blue-500 shadow-lg" />
                <h1 class="text-4xl font-extrabold text-gray-800 tracking-tight">Rico Posas</h1>
                <p class="text-sm text-gray-600">This is a Personal Page of Rico Martin Carl V. Posas</p>
            </header>

            <section>
                <h2 class="text-xl font-semibold mb-4 border-b pb-1 border-gray-300 text-gray-700">About Me</h2>
                <p class="leading-relaxed text-gray-700">
                    I'm a software developer focused on building accessible, performant apps with Vue.js and Nuxt.
                    I love clean design and scalable architecture.
                </p>
            </section>

            <section>
                <h2 class="text-xl font-semibold mb-4 border-b pb-1 border-gray-300 text-gray-700">Education</h2>
                <p class="leading-relaxed text-gray-700">
                    Visayas State University - BSCS
                </p>
            </section>

            <section>
                <h2 class="text-xl font-semibold mb-4 border-b pb-1 border-gray-300 text-gray-700">Skills</h2>
                <p class="leading-relaxed text-gray-700">
                    "Vue.js" , "Nuxt 3" , "JavaScript" , "TypeScript" ,
                    "C++" , "Node.js" , "C#" , "Git" , "Python" , "MYSQL"
                </p>
            </section>

            <section>
                <h2 class="text-xl font-semibold mb-4 border-b pb-1 border-gray-300 text-gray-700">Contact</h2>
                <p>Email: <a href="mailto:ricoposas@gmail.com" class="text-blue-600 hover:underline">ricoposas@gmail.com</a></p>
                <p>GitHub: <a href="https://github.com/Kissu1" target="_blank" class="text-blue-600 hover:underline">github.com/Kissu1</a></p>
            </section>
        </div>
    </div>
</template>

<style scoped>
    body {
        font-family: 'Inter', sans-serif;
        background-color: #f9fafb;
    }

    ul li:hover {
        background-color: #f1f5f9;
        transform: translateY(-5px);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    section {
        background-color: rgba(255, 255, 255, 0.9);
        border-radius: 12px;
        padding: 20px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        margin-bottom: 20px;
    }

        section:hover {
            background-color: rgba(255, 255, 255, 1);
        }

    span {
        transition: all 0.3s ease;
    }

        span:hover {
            transform: scale(1.05);
        }

    p {
        font-size: 16px;
    }

    a {
        transition: color 0.3s ease-in-out;
    }

        a:hover {
            color: #1e40af;
        }
</style>
