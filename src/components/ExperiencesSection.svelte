<script lang="ts">
import { Briefcase, Calendar } from "@lucide/svelte";

const experiences = [
    {
        title: "Fullstack Developer (Backend Specialist)",
        company: "Notus Labs",
        period: "January 2023 - Present",
        isCurrentJob: true,
        achievements: [
            "Engineered a high-performance scraper service processing over 960,000 data points per hour",
            "Led infrastructure migration to managed hosting, reducing costs by 30%+",
            "Improved development efficiency through new tools and practices",
            "Developed Chainless finance app with crypto and PIX integration, winning Avalanche hackathon",
            "Created dynamic CMS website for Florianópolis City Hall's Rede de Planejamento",
        ],
        technologies: [
            "GCP",
            "Linux",
            "TypeScript",
            "NestJS",
            "MongoDB",
            "Postgres",
            "NextJS",
            "Svelte",
            "Clean Architecture",
            "SOLID",
            "DDD",
        ],
    },
    {
        title: "Voluntary Junior Back End Developer",
        company: "Tech Pro Bem",
        period: "July 2022 - October 2022",
        isCurrentJob: false,
        achievements: [
            "Participated in solution definition and project structuring with Front End team",
            "Implemented API integrations and ensured data security",
            "Performed unit testing and AWS resource optimization",
            "Collaborated across teams (Front-end, Back-End, PO, QA)",
            "Received mentoring from senior developers",
        ],
        technologies: [
            "AWS",
            "NodeJS",
            "CI/CD",
            "Postgres",
            "OAuth2",
            "TypeScript",
            "Clean Architecture",
            "SOLID",
            "DDD",
        ],
    },
];
</script>

<section>
    <div class="flex items-center gap-4 mb-12">
        <Briefcase class="w-8 h-8 text-muted-foreground" />
        <h2 class="text-3xl lg:text-4xl font-bold tracking-tight">
            Experiences
        </h2>
    </div>

    <div class="space-y-12">
        {#each experiences as experience}
        <div class="relative pl-8 border-l border-border">
            <div
                class={`absolute -left-2 top-0 w-4 h-4 bg-background border-2 rounded-full ${
                    experience.isCurrentJob
                        ? "border-foreground"
                        : "border-muted-foreground"
                }`}
            ></div>
            <div class="space-y-4">
                <div>
                    <h3 class="text-xl lg:text-2xl font-semibold mb-1">
                        {experience.title}
                    </h3>
                    <div class="flex items-center gap-2 text-muted-foreground mb-2">
                        <span class="font-medium">
                            {experience.company}
                        </span>
                        <span>•</span>
                        <div class="flex items-center gap-1">
                            <Calendar size={14} />
                            <span class="text-sm">
                                {experience.period}
                            </span>
                        </div>
                    </div>
                </div>

                <ul class="space-y-2 text-muted-foreground">
                    {#each experience.achievements as achievement}
                    <li class="flex items-start gap-2">
                        <span class="w-1.5 h-1.5 bg-muted-foreground rounded-full mt-2 shrink-0"></span>
                        <span>{achievement}</span>
                    </li>
                    {/each}
                </ul>

                <div class="flex flex-wrap gap-1.5 pt-2">
                    {#each experience.technologies as tech}
                        <span class="px-2 py-1 bg-muted text-muted-foreground rounded text-xs font-medium">
                            {tech}
                        </span>
                    {/each}
                </div>
            </div>
        </div>
        {/each}

    </div>
</section>

