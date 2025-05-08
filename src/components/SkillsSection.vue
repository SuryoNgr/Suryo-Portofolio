<template>
    <section id="skills" class="skills bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-8">Skills</h2>
            <div class="skills-container grid grid-cols-2 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4">
                <div
                    v-for="(skill, index) in skillsList"
                    :key="index"
                    class="skill bg-gray-800 p-6 rounded-lg shadow-md flex flex-col items-center transition-transform transform hover:scale-105"
                >
                    <i v-if="skill.iconClass" :class="skill.iconClass + ' text-primary text-6xl mb-2'"></i>
                    <span v-else class="text-primary text-6xl mb-2" v-html="skill.icon"></span>
                    <h4 class="text-xl font-semibold">{{ skill.name }}</h4>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            skillsList: [
                {
                    name: "HTML",
                    iconClass: "fab fa-html5"
                },
                {
                    name: "CSS",
                    iconClass: "fab fa-css3-alt"
                },
                {
                    name: "JavaScript",
                    iconClass: "fab fa-js"
                },
                {
                    name: "PHP",
                    iconClass: "fab fa-php"
                },
                {
                    name: "Wordpress",
                    iconClass: "fab fa-wordpress"
                },
                {
                    name: "Tailwind CSS",
                    icon: `
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" width="64" height="64">
                            <path d="M12 6.036c-2.667 0-4.333 1.325-5 3.976 1-1.325 2.167-1.822 3.5-1.491.761.189 1.305.738 1.906 1.345C13.387 10.855 14.522 12 17 12c2.667 0 4.333-1.325 5-3.976-1 1.325-2.166 1.822-3.5 1.491-.761-.189-1.305-.738-1.907-1.345-.98-.99-2.114-2.134-4.593-2.134zM7 12c-2.667 0-4.333 1.325-5 3.976 1-1.326 2.167-1.822 3.5-1.491.761.189 1.305.738 1.907 1.345.98.989 2.115 2.134 4.594 2.134 2.667 0 4.333-1.325 5-3.976-1 1.325-2.167 1.822-3.5 1.491-.761-.189-1.305-.738-1.906-1.345C10.613 13.145 9.478 12 7 12z"/>
                        </svg>`
                },
                {
                    name: "Java",
                    iconClass: "fab fa-java"
                },
                {
                    name: "Vue.js",
                    icon: `
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 261.76 226.69" fill="currentColor" width="64" height="64">
                            <path d="M0 0l130.91 226.69L261.76 0H209.24l-78.33 135.19L52.58 0H0zm87.22 14.86h33.42L130.91 36l10.27-21.14h33.43L130.91 88.29z"/>
                        </svg>`
                },
                {
                    name: "Bootstrap",
                    iconClass: "fab fa-bootstrap"
                },
                {
                    name: "Git",
                    iconClass: "fa-brands fa-git-alt"
                }
            ]
        }
    }
}
</script>

<style scoped>
.skills {
    background: linear-gradient(135deg, #111827 0%, #14143d 100%);
}

.skills-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
}

@media (min-width: 768px) {
    .skills-container {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media (min-width: 1024px) {
    .skills-container {
        grid-template-columns: repeat(5, 1fr);
    }
}

.skill {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: transform 0.3s;
}

.skill h4 {
    margin-top: 1rem;
}
</style>
