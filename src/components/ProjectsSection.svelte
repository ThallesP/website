<script lang="ts">
  import { Code, ExternalLink } from "@lucide/svelte";
  import IPhoneMockup from "./IPhoneMockup.svelte";
  import DesktopMockup from "./DesktopMockup.svelte";

  type ProjectVisual = {
    type: "iphone" | "desktop";
    src: string; // image URL or path under /public
  };

  type Project = {
    title: string;
    description: string;
    url: string;
    displayUrl: string;
    visual: ProjectVisual;
    label?: string;
  };

  const projects: Project[] = [
    // {
    //   title: "Chainless",
    //   description:
    //     "Bootstrapped the backend infrastructure and was principal responsible in early days. Implemented comprehensive KYC system on the backend and developed complete features from end-to-end. Led technical decisions and architecture design for the core platform functionality.",
    //   url: "https://chainless.finance",
    //   displayUrl: "chainless.finance",
    //   visual: { type: "iphone", src: "/chainless-home.svg" },
    //   label: "Fintech",
    // },
    // {
    //   title: "Heimdall",
    //   description:
    //     "Bootstrapped the backend infrastructure and was principal responsible for backend development. Implemented managed hosting infrastructure reducing costs by 30% and doubling productivity in deployments per day. Built a reliable data scraper system processing over 16k inserts per minute.",
    //   url: "https://heimdall-frontend.vercel.app/",
    //   displayUrl: "heimdall-frontend.vercel.app",
    //   visual: { type: "desktop", src: "/favicon.svg" },
    //   label: "Platform",
    // },
    {
      title: "Notus API",
      description:
        "Built Notus's admin dashboard and its dedicated backend infrastructure as part of a development team. Principal responsible for both dashboard frontend and backend as a fullstack developer. Developed the entire billing system with pay-as-you-go functionality and delivered core dashboard components within a 3-month timeline.",
      url: "https://dashboard.notus.team",
      displayUrl: "dashboard.notus.team",
      visual: { type: "desktop", src: "/notus-dashboard-image.png" },
      label: "Dashboard",
    },
    {
      title: "Rede de Planejamento",
      description:
        "Contributed to designing and deploying a dynamic website with customizable content management for Florianópolis City Hall as part of a team, significantly reducing time required to manage static content and improving operational efficiency. Developed a powerful GraphQL endpoint with complex data model relationships.",
      url: "https://redeplanejamento.pmf.sc.gov.br",
      displayUrl: "redeplanejamento.pmf.sc.gov.br",
      visual: { type: "desktop", src: "/rede-de-planejamento-image.png" },
      label: "GovTech",
    },
  ];
</script>

<section>
  <div class="flex items-center gap-4 mb-12">
    <Code class="w-8 h-8 text-muted-foreground" />
    <h2 class="text-3xl lg:text-4xl font-bold tracking-tight">Projects</h2>
  </div>

  <div class="flex flex-col gap-12 md:gap-14">
    {#each projects as project}
      <article class="group relative max-w-4xl mx-auto w-full">
        <div
          class="absolute inset-0 -z-10 rounded-2xl opacity-30 blur-xl bg-gradient-to-r from-purple-500/20 via-cyan-500/10 to-fuchsia-500/20"
        ></div>
        <div class="overflow-hidden rounded-xl border border-border bg-card/40">
          <div class="relative overflow-hidden">
            {#if project.visual.type === "iphone"}
              <div class="w-full overflow-hidden">
                <div
                  class="w-full h-full origin-top px-6 md:px-12 pt-6 md:pt-10"
                >
                  <IPhoneMockup src={project.visual.src} class="h-1/2" />
                </div>
              </div>
            {:else if project.visual.type === "desktop"}
              <div
                class="w-full aspect-[21/9] md:aspect-[20/9] overflow-hidden"
              >
                <div class="w-full h-[200%] transform scale-125 origin-top">
                  <DesktopMockup
                    imageSrc={project.visual.src}
                    url={project.displayUrl}
                    style="width: 100%; height: auto; display: block;"
                  />
                </div>
              </div>
            {/if}
            <div
              class="pointer-events-none absolute inset-0 bg-gradient-to-t from-background/70 via-transparent to-transparent"
            ></div>
          </div>
          <div class="p-5">
            <div class="mb-2 flex items-center gap-2">
              {#if project.label}
                <span
                  class="inline-flex items-center rounded-full bg-muted px-2 py-0.5 text-xs font-medium text-muted-foreground"
                >
                  {project.label}
                </span>
              {/if}
            </div>
            <h3 class="text-lg lg:text-xl font-semibold">
              {project.title}
            </h3>
            <p class="mt-2 text-muted-foreground text-sm leading-relaxed">
              {project.description}
            </p>
            <a
              href={project.url}
              target="_blank"
              class="mt-4 inline-flex items-center gap-2 text-sm hover:underline underline-offset-4 transition-colors"
            >
              <span>{project.displayUrl}</span>
              <ExternalLink size={14} />
            </a>
          </div>
        </div>
      </article>
    {/each}
  </div>
</section>
