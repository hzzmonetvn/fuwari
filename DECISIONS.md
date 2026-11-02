# Decisions

- Set Astro's canonical site URL to `https://hzzmonet.io.vn/` so generated sitemap, RSS, and canonical URLs use the intended domain. Kept the existing static Astro build rather than adding a framework adapter; Cloudflare Pages can build and serve the static output.
- Added About, Contact, Privacy, and Terms information to navigation/footer to make key site information discoverable. Used the existing GitHub and Telegram profiles as contact methods because no public email was provided.
- Marked obvious Fuwari demonstration posts as drafts instead of deleting them, preserving them for reference while keeping them out of the public blog until replaced by original content.
- Did not add AdSense publisher/script IDs because no publisher ID was provided and ads are not yet active.
- Replaced the homepage banner with `bg.jpg` from `hzzmonetvn/keyboxhub-web` and disabled the old Honkai artwork credit because it no longer describes the displayed image.
- Did not create a GitHub Actions deploy workflow: Cloudflare Pages was said to already exist, and connecting GitHub through the Cloudflare dashboard avoids storing deployment credentials in the repository.
- Push and deployment remain pending because this environment has no GitHub HTTPS credentials. Build validation is also blocked by an existing Tailwind CSS error in `src/styles/markdown.css`; `astro check` reports existing errors in `src/components/Navbar.astro` and `src/pages/archive.astro`.
