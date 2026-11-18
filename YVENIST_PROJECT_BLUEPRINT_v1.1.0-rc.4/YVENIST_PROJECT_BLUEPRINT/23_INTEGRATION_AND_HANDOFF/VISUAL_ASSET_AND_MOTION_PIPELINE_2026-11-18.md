# VISUAL ASSET AND MOTION PIPELINE — 2026-11-18

**Status:** RECOMMENDED_WORKFLOW / TOOL_SELECTION_AND_BUDGET_REVIEW_PENDING  
**Owners' direction:** new app-icon explorations; establish a visual language for 2D/3D illustrations and icons; use Claude and ChatGPT to research, propose, produce and present alternatives across all Blueprint stages; animation/performance review should be a design gate where practicable.

## 1. Recommended toolchain

Use a small, interoperable toolchain rather than adding every available design application.

| Need | Recommended tool | Role | Why |
|---|---|---|---|
| Brand, component and vector illustration source | Figma | Design system, editable vectors, layouts, handoff, review and approval | Already used as the visual source of truth. Keep source assets editable and organized. |
| Interactive 2D animation and UI motion | Rive | Draw/rig/animate interactive vector assets; state machines; export .riv for the Flutter runtime | Rive provides a design tool plus Flutter runtime and supports state-driven interactions. |
| Lightweight decorative/linear motion | Lottie + After Effects/Bodymovin where available | Export deterministic decorative animations to JSON for Flutter | The Flutter Lottie package renders After Effects/Bodymovin exports. Use for bounded, non-interactive animations. |
| 3D asset modelling and animation | Blender | Build low-poly/stylized 3D assets, materials, lighting and animation; export optimized glTF/GLB when runtime 3D is truly needed | Blender's glTF exporter supports mesh, materials, textures and animation. |
| Raster concept exploration | Image-generation tool, followed by human/vector cleanup | Explore art direction, composition and moodboards | Generated raster images are concept inputs; do not treat them as editable source vectors, production-ready icons or a substitute for a coherent asset system. |
| Code, CLI, integration and automated checks | Claude Code in terminal | Create scripts, manage asset pipelines, integrate Flutter runtimes, write tests and prepare previews | The owner-confirmed environment is Windows native + terminal. Every installation and command must be reviewed before execution. |
| Product critique, research and approval preparation | ChatGPT + Claude | Compare alternatives, check consistency, prepare briefs and acceptance criteria | AI recommendations remain proposals; owners approve brand and commercial decisions. |

Primary technical references:
- Rive Flutter runtime: https://pub.dev/documentation/rive/latest/
- Rive Flutter repository and CLI/agent workflow: https://github.com/rive-app/rive-flutter
- Lottie for Flutter: https://pub.dev/packages/lottie
- Blender glTF 2.0 export manual: https://docs.blender.org/manual/en/4.0/addons/import_export/scene_gltf2.html

## 2. Preferred implementation split

- **Rive:** primary choice for interactive 2D characters, mascots, animated icons, celebration sequences and stateful UI animations.
- **Lottie:** simple, self-contained decorative animations (confetti bursts, small success celebrations, non-interactive loops) where the exported file remains small and performant.
- **Blender/3D:** use selectively for signature campaign/hero assets or special scenes. Do not render every common UI icon in 3D; this increases asset weight, visual noise and device cost.
- **Native Flutter:** transitions, micro-interactions, loading indicators and simple property animations should remain native when this is simpler and faster than an external animation runtime.

The visual language should feel like one family: consistent silhouettes, stroke/edge treatment, perspective, shadows, material, color roles, rhythm and motion curves. 2D and 3D may coexist, but only under a documented art direction.

## 3. Asset families to create

1. Brand marks and app icon.
2. Core UI icons (Material Icons mapping remains the approved UI icon source; do not replace it wholesale with illustrative icons).
3. 2D brand illustrations and empty-state scenes.
4. 3D hero/seasonal illustrations where they add value.
5. Animated brand moments (onboarding, Party Maker milestones, paid-order success, celebration).
6. Feedback/status motion (loading, success, error, progress) with reduced-motion alternatives.
7. Marketing/store assets, separate from in-app functional assets.

Distinguish **functional icons** from **brand illustrations**. Functional icons should remain predictable and accessible; the illustration system may express personality.

## 4. Asset specification and file governance

Every production asset should have:
- asset ID, name, purpose, owner and approval status;
- original editable source and tool/version;
- light/dark variants and contrast/background constraints;
- export format, pixel/vector dimensions, scale and target density;
- animation trigger, duration, loop, entry/exit, easing and stop conditions;
- fallback/static frame and reduced-motion behavior;
- file-size budget and device-performance evidence;
- license, author/source and third-party dependency details.

Recommended naming: `category_subject_variant_state_version.ext`. Keep sources and exports in separate folders; only approved exports enter Flutter assets. Store a preview image/GIF/video and implementation note beside each animated asset.

## 5. Mandatory design/performance approval gate

For every significant animation and for the assembled core flows:
- define user purpose and trigger; remove motion that does not explain state or help the task;
- document normal, reduced-motion and static fallback states;
- check light/dark surfaces, contrast, clipping, text scaling and screen-reader semantics;
- test on the nominated entry-level Android device with a **release** build, not only a debug build;
- measure cold start, time to interactive, scroll/render smoothness, jank, memory, CPU/GPU, battery/thermal effect and asset size;
- test poor/unstable network separately from device rendering;
- capture a short recording and attach the device/build/version/test result;
- resolve severe visual/performance/accessibility defects before design approval.

Android Developers recommends using a lower-end physical device to expose performance bottlenecks, testing release builds, measuring startup and scrolling/animation behaviour, and notes that most apps should aim for 60 fps without dropped or delayed frames.

Reference device recommendation for this project: **Samsung Galaxy A17 5G, Brazilian 4 GB RAM / 128 GB variant (SM-A176B)**. It is a current entry-level class device with a 90 Hz 6.7-inch display and Exynos 1330 listed in Samsung's Brazilian documentation. Use it as a repeatable project reference, not as the minimum Android compatibility definition. When budget permits, add a second older/cheaper 4 GB device as a stress-test device. Confirm the exact RAM/storage SKU at purchase; Samsung may offer other configurations.

Performance test setup:
- cold start after force-stop and after clean install;
- no background apps, controlled battery level and stable Wi-Fi for repeatability;
- test core Home, Explore, Party Maker, detail, cart/checkout, confirmation and animation states;
- run at least 3 repeated attempts and report median plus worst case;
- document Android/One UI version, device model, build SHA, Flutter version and animation runtime version.

## 6. How Claude and ChatGPT should work across every stage

At the start of a task, Claude should present a short **tool and skill plan**:
- applicable project skills/agents;
- exact CLI tools, Figma integrations, MCP servers and libraries proposed;
- whether each tool is already installed, requires installation, has a cost/account requirement or touches external data;
- outputs it will create and where;
- commands or migrations with risk;
- preview/verification plan and approval checkpoint.

Claude should not install new tools, add production dependencies, publish assets, overwrite Figma frames or change project-wide standards without surfacing the impact first. For low-risk local exploration, it can proceed within the agreed workspace and report the result.

For every visual proposal, ask Claude to provide:
1. at least 2–3 genuinely different alternatives where a choice exists;
2. a preview in context (not only a standalone export);
3. source/editable file plus production export;
4. variants for light/dark, small/large and reduced-motion where relevant;
5. file size, runtime/dependency and target-device impact;
6. accessibility and consistency review;
7. clear recommendation with reasons and unresolved trade-offs.

ChatGPT should act as research/critique and decision-support partner: verify current tool capabilities, compare approaches, identify accessibility/performance risks and produce decision briefs. Do not have the AI silently choose the brand identity or finalize an asset.

## 7. First recommended work sequence

1. Freeze the new approved color `#FF5637`, Plus Jakarta Sans and approved Material Icons mapping in the design decision record.
2. Refine semantic design tokens, including accessible foreground combinations for the new coral.
3. Create an illustration art-direction board (shape language, line/edge, material, shading, perspective, color, personality).
4. Explore new app-icon routes against store-size legibility and trademark distinctiveness.
5. Build one representative 2D illustration in Figma/Rive and one simple animation prototype.
6. Add one selective 3D hero concept in Blender only if it strengthens the visual direction.
7. Integrate a small pilot into Flutter and benchmark on the Galaxy A17 5G.
8. Approve the reusable asset system before producing the full illustration catalogue.

## 8. References

- Android performance journey: https://developer.android.com/blog/posts/leveling-guide-for-your-performance-journey
- Android performance test environment: https://developer.android.com/topic/performance/appstartup/setup-env
- Android technical quality and rendering: https://developer.android.com/quality/technical
- Samsung Galaxy A17 Brazil announcement/specifications: https://news.samsung.com/br/feitos-para-durar-samsung-apresenta-galaxy-a17-e-galaxy-a07-no-brasil-com-armazenamento-robusto-recursos-ai-processador-de-alto-desempenho-e-ate-6-anos-de-atualizacoes
- Samsung Galaxy A17 5G Brazil product page: https://www.samsung.com/br/smartphones/galaxy-a/galaxy-a17-5g-gray-128gb-sm-a176bzaozto/

This is a recommended production pipeline. Purchase/licensing decisions and dependency choices remain subject to cost, compatibility and owner review.
