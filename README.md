# ryanweldzius.com

Personal academic website, hosted on GitHub Pages. GitHub rebuilds the site
automatically about a minute after any change is pushed or saved on github.com.

## Add a paper

1. Open the file for its section in `_data/research/`:

   | Section on the page                   | File                |
   |---------------------------------------|---------------------|
   | Book Projects                         | `books.yml`         |
   | Peer-Reviewed Publications            | `peer_reviewed.yml` |
   | Other Publications                    | `other.yml`         |
   | Working Papers & Works in Progress    | `working.yml`       |

2. Paste a new block at the **top** of the list (below the comments):

   ```yaml
   - title: "My New Paper: A Subtitle"
     authors: "Ryan Weldzius and Coauthor Name"
     year: 2027
     venue: "International Organization"
     details: "81(2): 1–30"
     abstract: >
       First paragraph of the abstract. Line breaks inside a paragraph
       don't matter.

       A blank line starts a new paragraph.
     links:
       - label: Paper
         url: https://doi.org/...
       - label: Appendix
         url: files/my_appendix.pdf
   ```

   Every field except `title` is optional. For a working paper, just use
   `title`, `note: "with Coauthor Name"`, and `abstract`.

3. **Wrap values in "double quotes"** if they contain a colon followed by a
   space (most titles with subtitles do).

To move a paper from "Working Papers" to "Peer-Reviewed" once it is accepted, cut its block from one
file and paste it at the top of the other, then add `authors`, `year`, `venue`,
and `details`.

You can edit these files directly on github.com (open the file and click the
pencil icon). If the page doesn't update, check the **Actions** tab on GitHub for
a red X; it usually means an indentation or quoting mistake in the YAML.

## Other updates

- **CV:** replace `files/weldzius_cv.pdf` with the new PDF, keeping the same name.
- **Syllabi and other PDFs:** put them in `files/` and link them as `files/name.pdf`.
- **Menu:** edit `nav:` in `_config.yml`.
- **New Shiny app page:** copy `supply-chain-vulnerability.html`, change the
  `title`, `app_url`, and `app_height`, then add it under Data Viz in `_config.yml`.

## Preview locally (optional)

```bash
PATH=/opt/homebrew/opt/ruby@3.3/bin:$HOME/.local/share/gem/ruby/3.3.0/bin:$PATH jekyll serve
```

Then open http://localhost:4000.
