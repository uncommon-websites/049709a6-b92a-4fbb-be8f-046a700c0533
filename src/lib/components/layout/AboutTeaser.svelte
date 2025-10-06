<!--
@component AboutTeaser
A minimalist teaser for the about page featuring the founder's story.
-->
<script lang="ts">
	// Types
	type TeamMember = {
		name: string;
		role: string;
		image: string;
	};

	// Components
	import Button from "../ui/Button.svelte";
	import ScrollText from "./sub/ScrollText.svelte";

	// State
	let sectionRef: HTMLElement;

	let props = $props();

	// Data
	const teamMember: TeamMember = {
		name: "Jordan Chen",
		role: "Founder & Creative Director",
		image: "/generated/image-a-professional-founder-in-a-modern-desig.webp"
	};
</script>

<section bind:this={sectionRef} {...props}>
	<div class="section-px section-py container mx-auto">
		<div class="relative mx-auto grid max-w-2xl place-items-center gap-16">
			<ScrollText
				class="text-title1 text-center"
				text={`"After watching too many great startups stall for months waiting on website launches, I knew there had to be a better way. We built this agency to prove that speed and quality aren't mutually exclusive when you truly master your tools."`}
			/>

			<!-- Team Member & CTA Section -->
			<div class="grid items-center gap-8">
				<div class="flex items-center justify-start gap-4">
					<img
						src={teamMember.image}
						alt={teamMember.name}
						class="size-12 rounded-full object-cover"
					/>
					<div>
						<div class="text-callout">{teamMember.name}</div>
						<div class="text-caption text-muted-foreground">{teamMember.role}</div>
					</div>
					<Button href="/about" variant="secondary" size="sm" class="ml-8">Read our story</Button>
				</div>
			</div>
		</div>
	</div>
</section>
