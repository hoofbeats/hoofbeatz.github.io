## A static, AMP-formatted site

### Installation

#### Jekyll

  ##### Revert Jekyll formatting
  1. Remove this line to your Jekyll site's `Gemfile`:

    ```RUBY
    gem "minima"
    ```

  2. And remove this line from your Jekyll `_config.yml` file:

    ```YAML
    theme: minima
    ```

  3. And then execute:

    ```
    $ bundle
    ```

  ##### Jekyll Customization
  - To override the default structure and style of Jekyll's default minima theme:
  1. Grab all of the minima theme hidden files via `bundle show minima`.
    - Personalize these files (i.e. `_config.yml`) as you wish
  2. For `_includes/head.html `, goal is to meet Google's [AMP specifications]().
  3. Create `head` folder in `_includes`
    - Add the following files to `_includes/head` folder:
      - `_meta.html`,
      - `_meta-google.html`,
      - `_meta-twitter.html`,
      - `metadata.json`
      - `script-twitter.html`,
      - `scripts-amp.html`,
      - `style-amp.html`
    - The latter of these files will house AMP's inline CSS, but for now, we'll leave `assets/main.scss` where it is & with its frontmatter to avoid breaking Jekyll's build (To *override the default CSS*, the file has to exist at your site source).

### Development
  - To set up your environment to develop this theme, run `bundle install`.
  - To test your theme, run `bundle exec rake preview` and open your browser at `http://localhost:4000/minima/`. This starts a Jekyll server using your theme and the contents of the `example/` directory. As you make modifications to your theme and to the example site, your site will regenerate and you should see the changes in the browser after a refresh.

### Future Tasks
  - [ ] Enabling Google Analytics
    - To enable Google Anaytics, add the following lines to your Jekyll site:

      ```yaml
        google_analytics: UA-NNNNNNNN-N
      ```

    - Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

  - [ ] Enabling comments (via Disqus)
    - Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each post.
    - To enable it, add the following lines to your Jekyll site:

      ```yaml
        disqus:
          shortname: my_disqus_shortname
      ```

    - You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).
    - Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`
    - If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.
