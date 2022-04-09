# abbieschenk.com

The code for my website that runs on Hugo.

To start this locally, run `hugo server` in the terminal.

This site is deployed on [https://abbieschenk.com](https://abbieschenk.com) via Netlify.

The theme is a separate git submodule, also [hosted on GitHub](https://github.com/abbieschenk/hugo-theme-abbieschenk). To make changes to the theme of this site:

1. Update the theme locally
2. Commit the changes in the themes/hugo-theme-abbieschenk directory (`git commit -am "some message"`)
3. Push the changes in the themes/hugo-theme-abbieschenk directory to the theme GitHub repo (`git push`)
4. Commit the changes in this directory (for abbieschenk.com) locally
5. Push the changes in this directory (for abbieschenk.com) to GitHub
6. Netlify will automatically rebuild the site.