# Backend Atlas

A responsive, static backend and system-design learning website. Built with HTML, CSS and vanilla JavaScript. No build step, API keys, database, or package installation is needed.

## Run

Open `dist/index.html` directly in a browser, or serve `dist/` with any static server (for example `python -m http.server 8080 --directory dist`). Deploy the contents of `dist/` to a static host. Hash-based routes do not need server rewrites.

## Contents

- 120 lessons in 17 chapters, covering the supplied curriculum and attached topics.
- About 21,000 words, 240 examples, and one four-stage guided visual model per lesson.
- Nine stateful experiments: HTTP, LRU cache, token bucket, round-robin load balancing, worker queue, binary search, PostgreSQL isolation, circuit breaker, and modulo hash sharding.
- Search, bookmarks, explicit completion tracking, resume, progress export, light/dark mode, and print styling.
- Three verified YouTube explainers embedded on demand; other lessons link to topic-specific YouTube searches, clearly labeled as uncurated search results.
- Primary documentation resources linked from each lesson.

## Edit content

`build_content.py` is the editable course source. Run `python build_content.py` to regenerate `dist/content.js` using only the Python standard library. The application reads that bundled content without fetch, so direct file opening works.

- `dist/index.html`: shell and navigation
- `dist/styles.css`: responsive layout and themes
- `dist/app.js`: navigation, search, progress, traces, and live experiments
- `dist/content.js`: bundled lesson content

The optional Google Fonts stylesheet needs internet; system-font fallbacks are configured. YouTube and external documentation require internet. Learning content and simulations are browser-local. Browser storage can vary for file:// URLs or private browsing; use a normal static origin for reliable persistence.

## Model boundaries

All simulations are teaching models. HTTP does not issue real requests; the queue does not run a broker; isolation shows a specific PostgreSQL read schedule; circuit timing and token time advance manually; the sharding experiment demonstrates modulo hashing rather than a full consistent-hashing implementation. Walkthrough timings are illustrative and are not benchmarks.

## Validation

JavaScript syntax checks passed. Content validation checked unique IDs, two examples, documentation/video-search links, and four labeled stages for every lesson. Browser QA exercised all nine experiments, search, bookmarking/completion, and a 390-pixel mobile viewport including drawer navigation and HTTP controls.
