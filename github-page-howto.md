# Turn your Github repository into a website

Github offers a great feature which allows you to use your repository as a free server for hosting a website. You can turn your repository into a website visible at *\<username\>.github.io/\<repo-name\>* (or a [custom domain name](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)) by doing the following (updated instructions from [here](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-your-site)):
- Make your repo public (in the *Settings*, bottom of **General** tab)
- Then click the **Pages** tab:
  - choose your `main` branch as the Source
  - make sure */root* is selected
  - click **Save**
- You can tell if a Github repo is deployable as a website when:
  - On the right-hand pane, under **Environments**, there is a *github-pages* link.
  - After clicking this link, in the following page, you are able to view the site by clicking the topmost **View deployment** link. This should display your latest pushed commits.
  
Note that when visiting *\<username\>.github.io/\<repo-name\>*, you may want to perform a hard refresh (Ctrl+Shift+R) to view the latest pushed commits. Note also that *GitHub Pages will look for an `index.html`, `index.md`, or `README.md` file as the entry file for your site.*
