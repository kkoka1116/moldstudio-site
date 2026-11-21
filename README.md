# MoldStudio website and releases

The public site for MoldStudio (https://kkoka1116.github.io/moldstudio-site/): what it is, a clinician
walkthrough, the privacy statement, and the macOS download.

- **Releases** hold the app (`MoldStudio-macOS-arm64.zip`). `latest.json` and `latest.json.sig` are the
  signed update feed the installed app checks; they are written by `packaging/release.py` in the
  MoldStudio source repository and signed with a key that is not stored here.
- MoldStudio is a research alpha and **not a medical device**. The treating clinician is responsible for
  every design and every clinical decision.
- The screenshots were taken on one de-identified scan of a stone model (a right unilateral cleft): no names and no dates.

## Counting visitors and downloads

- **Page views:** every page loads GoatCounter's cookieless counter for the site code `moldstudio`
  (dashboard at https://moldstudio.goatcounter.com once that account exists; GoatCounter is free for
  non-commercial use). It stores no IP address and sets no cookie; `privacy.html` says so.
- **Downloads:** GitHub counts each download of each release file. To read the counts:

  ```bash
  gh api repos/kkoka1116/moldstudio-site/releases --paginate \
    --jq '.[] | .tag_name as $t | .assets[] | "\($t)\t\(.name)\t\(.download_count)"'
  ```

  The count is a plain number per file: GitHub reports nothing about who downloaded it.
