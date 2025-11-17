# Google Dorking 

**Platform:** TryHackMe  
**Category:** OSINT / Recon  
**Difficulty:** Beginner  
**Date Completed:** 2025-11-07
**Author:** irsam 
---

## Overview

This write-up documents my walkthrough of the **Google Dorking** room.  
During this room I learned and practiced: **SEO basics, web crawling concepts, robots.txt, sitemaps, and Google dorking** to discover publicly exposed information. The focus is on safe, ethical reconnaissance and understanding how publicly-surfaced data can reveal sensitive content.

---

## Topics Covered

- **SEO basics** — how search engines index pages and why content appears in search results.  
- **Web crawling** — how crawlers (bots) discover pages; crawl priority and indexing.  
- **robots.txt** — how `robots.txt` works, its syntax, and how it can (sometimes) leak paths.  
- **Sitemaps** — `sitemap.xml` purpose and how it helps find site structure and hidden pages.  
- **Google Dorking** — search operators and example dorks (`site:`, `inurl:`, `intitle:`, `filetype:`, `ext:`, `intitle:` etc).

---

## Tools & Resources

- Browser (Chrome/Firefox)  
- Search engine (Google) — practice dorks locally or on allowed targets only  
- Notes / screenshots saved in `screenshots/` folder

---

## Learning Objectives

- Understand how SEO and crawler behavior affect what’s discoverable.  
- Identify useful search operators for targeted discovery.  
- Learn how to check `robots.txt` and `sitemap.xml` for potential info.  
- Practice writing safe Google dorks to find publicly-available data.

---

## Walkthrough / Steps

1. **Intro — SEO & Crawling**  
   - Quick note: Search engines crawl the web, build an index, then return results based on relevance.  
   - Important SEO signals: page titles, meta description, robots rules, sitemap presence.

2. **Check `robots.txt`**  
   - Visit `https://example.com/robots.txt` or fetch with `curl`:
     ```bash
     curl -s https://example.com/robots.txt
     ```
   - Note any `Disallow:` entries — these sometimes reveal paths the site owner preferred not to index.

3. **Check `sitemap.xml`**  
   - Visit `https://example.com/sitemap.xml` or `https://example.com/sitemap_index.xml`.
   - Sitemaps list pages and can reveal hidden endpoints or folders.

4. **Google Dorking: Operators & Examples**  
   - Basic operators used:
     - `site:example.com` — restricts results to a domain  
     - `inurl:admin`, `intitle:"index of"` — find directory listings or admin pages  
     - `filetype:pdf` / `ext:pdf` — find files of specific types  
     - `intext:"password"` / `"sensitive term"` — find exposed strings
   - Example dorks (do not run on targets you don’t have permission to test):
     ```
     site:example.com inurl:login
     site:example.com filetype:pdf "confidential"
     site:example.com inurl:admin OR inurl:dashboard
     "index of" site:example.com
     ```



