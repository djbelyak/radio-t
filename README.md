# radio-t
[![Build Status](https://travis-ci.org/djbelyak/radio-t.svg?branch=master)](https://travis-ci.org/djbelyak/radio-t)

Hugo version of radio-t

Demo: [djbelyak.github.io](http://djbelyak.github.io/)

## User guide

### Requirements

- **Git** [(link)](https://git-scm.com/downloads)
- **Hugo** [(link)](https://github.com/spf13/hugo/releases) or [(link)](http://gohugo.io/#action)

### Build the static site

1. Get project from Github:
        
        $ cd ~/workdir
        $ git clone https://github.com/djbelyak/radio-t.git
        $ cd radio-t

2. Change base URL of site.
For this you should open file ~/workdir/radio-t/config.toml and repalce URL in the fistr string.
2. View the site locally. Do:

        $ hugo serve -t radio-t
and than open [http://localhost:1313/](http://localhost:1313/)

3. If your version of site looks good, generate a public version:

        $ hugo -t radio-t
Your public version will be located radio-t/public.
You may copy the content of this folder to web-server workdirectory.
4. If your version of site looks bad, please make an [issue](https://github.com/djbelyak/radio-t/issues/new)

### Add new content

1. Make new markdown file:

        $ cd ~/workdir/radio-t
        $ hugo new p/{filename}.markdown
2. Add information to ~/workdir/radio-t/content/p/{filename}.markdown file.
3. If you have static content, put it into ~/workdir/radio-t/static
3. Check view of new information

        $ hugo serve -t radio-t
and than open [http://localhost:1313/](http://localhost:1313/)

4. Generate public version:

        $ hugo -t radio-t
Your public version will be located radio-t/public.


