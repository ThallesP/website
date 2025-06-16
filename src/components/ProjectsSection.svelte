<script lang="ts">
    import { CardFooter, CardTitle } from "$lib/components/ui/card";
    import CardContent from "$lib/components/ui/card/card-content.svelte";
    import CardHeader from "$lib/components/ui/card/card-header.svelte";
    import Card from "$lib/components/ui/card/card.svelte";
import { Code, ExternalLink, Award, MapPin } from "@lucide/svelte";

const projects = [
    {
        title: "Chainless",
        description:
            "Bootstrapped the backend infrastructure and was principal responsible in early days. Implemented comprehensive KYC system on the backend and developed complete features from end-to-end. Led technical decisions and architecture design for the core platform functionality.",
        url: "https://chainless.finance",
        displayUrl: "chainless.finance",
        icon: "award",
    },
    {
        title: "Heimdall",
        description:
            "Bootstrapped the backend infrastructure and was principal responsible for backend development. Implemented managed hosting infrastructure reducing costs by 30% and doubling productivity in deployments per day. Built a reliable data scraper system processing over 16k inserts per minute.",
        url: "https://heimdall-frontend.vercel.app/",
        displayUrl: "heimdall-frontend.vercel.app",
        icon: "code",
    },
    {
        title: "Notus API",
        description:
            "Built Notus's admin dashboard and its dedicated backend infrastructure as part of a development team. Principal responsible for both dashboard frontend and backend as a fullstack developer. Developed the entire billing system with pay-as-you-go functionality and delivered core dashboard components within a 3-month timeline.",
        url: "https://dashboard.notus.team",
        displayUrl: "dashboard.notus.team",
        icon: "code",
    },
    {
        title: "Rede de Planejamento",
        description:
            "Contributed to designing and deploying a dynamic website with customizable content management for Florianópolis City Hall as part of a team, significantly reducing time required to manage static content and improving operational efficiency. Developed a powerful GraphQL endpoint with complex data model relationships.",
        url: "https://redeplanejamento.pmf.sc.gov.br",
        displayUrl: "redeplanejamento.pmf.sc.gov.br",
        icon: "map",
    },
];

const getIcon = (iconType: string) => {
    switch (iconType) {
        case "award":
            return Award;
        case "map":
            return MapPin;
        case "code":
            return Code;
        default:
            return Code;
    }
};
</script>

<section>
    <div class="flex items-center gap-4 mb-12">
        <Code class="w-8 h-8 text-muted-foreground" />
        <h2 class="text-3xl lg:text-4xl font-bold tracking-tight">Projects</h2>
    </div>

    <div class="grid gap-6 md:grid-cols-2">
        {#each projects as project}
        <Card class="bg-background !gap-2">
            <CardHeader class="flex items-center justify-between">
                <CardTitle>
                    {project.title}
                </CardTitle>
                <svelte:component this={getIcon(project.icon)} class="w-5 h-5 text-muted-foreground" />
            </CardHeader>
            <CardContent>
                <p class="text-muted-foreground mb-4 text-sm leading-relaxed">
                    {project.description}
                </p>
            </CardContent>
            <CardFooter class="flex items-start">
                <a
                    href={project.url}
                    target="_blank"
                    class="inline-flex items-center gap-2 text-sm hover:underline underline-offset-4 transition-colors"
                >
                    <span>{project.displayUrl}</span>
                    <ExternalLink size={14} />
                </a>
            </CardFooter>
        </Card>
        {/each}
    </div>
</section>
