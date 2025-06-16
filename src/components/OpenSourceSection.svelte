<script lang="ts">
import { Github } from "@lucide/svelte";

const openSourceProjects = [
    {
        title: "NestJS Better Auth",
        description:
            "A NestJS authentication module that provides a better way to handle authentication in your application.",
        githubUrl: "https://github.com/thallesp/nestjs-better-auth",
        repoName: "nestjs-better-auth",
    },
    {
        title: "WhatsApp Cloud.js",
        description:
            "A JavaScript/TypeScript client for the WhatsApp Cloud API with full type support.",
        githubUrl: "https://github.com/thallesp/whatsapp-cloud.js",
        repoName: "whatsapp-cloud.js",
    },
];
</script>

<section>
    <div class="flex items-center gap-4 mb-12">
        <Github class="w-8 h-8 text-muted-foreground" />
        <h2 class="text-3xl lg:text-4xl font-bold tracking-tight">
            Open Source
        </h2>
    </div>

    <div class="grid gap-6 md:grid-cols-2">
        {#each openSourceProjects as project}
        <div class="group border rounded-lg p-6 hover:bg-muted/50 transition-colors">
            <div class="flex items-start justify-between mb-3">
                <h3 class="text-lg font-semibold">{project.title}</h3>
                <Github class="w-5 h-5 text-muted-foreground" />
            </div>
            <p class="text-muted-foreground mb-4 text-sm leading-relaxed">
                {project.description}
            </p>
            <a
                href={project.githubUrl}
                target="_blank"
                class="inline-flex items-center gap-2 text-sm hover:underline underline-offset-4 transition-colors"
            >
                <Github size={14} />
                <span>{project.repoName}</span>
            </a>
        </div>
        {/each}
    </div>
</section>

