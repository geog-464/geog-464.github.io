Here are two alternative ways to run a Jupyter notebook without installing jupyterlab locally. The first uses Google Drive and is less directly integrated with Github, the second is less intuitive, but provides more direct interface with Github.

## To run the lab *online* using *Google Colab*

This option uses proprietary software with terms of use, requires a Google account and available space on Google Drive, and can't be integrated directly with your online Github repo, so it requires manual file management (i.e. downloading your work from Google Drive once completed and uploading it to Github for submission).

- Visit your [Google Drive]([https://colab.research.google.com/](https://drive.google.com)) and make sure you're logged in with your Google account
- If you would like to create a new Jupyter notebook, hit **New** > **More** > **Google Colaboratory**. Remember that you will need to then download this `ipynb` file and add it to your Github repo manually if you need to submit it later.
  - Or, if you need to work with an existing repo, clone or download (and unzip) your repo, then upload your whole repo folder to Google Drive
- From inside Google Drive, open your lab notebook (.ipynb) file: it should open automatically in Google Colab

### to import data to your Google Colab notebook
- Once in the lab notebook, click the files tab (folder icon) on the left,
- At the top of the panel that appears on the left, there are three icons: click the one furthest to the right to **Mount Drive**
- Run the code cell that appears in your notebook.
- After running, you should then have access to your Google Drive files and folders in the lefthand filebrowser pane
  - Note that you will need to use the full filepath for any data files you might need to import into your lab notebook (i.e. instead of loading something like "data.csv" which uses a relative path and assumes the file is in the same folder as your notebook, you would need to load it explicitly using the full path, such as "/content/drive/MyDrive/labX/data.csv"). Like in Jupyter Lab, you can keep track of where your files are in the file browser pane on the left.

## To run the lab *online* using *MyBinder*

This option uses open source infrastructure and can integrate directly with Github while being online, however it requires your Github repo to be set to *public*. It also can't save your work anywhere since each new session is temporary. A good workaround is to use `git push` to save your work (which means you should be pushing frequently if you don't want to lose any progress due to having accidentally closed your web browser!).

- Once you have forked this lab by using the Github Classroom link, go to your Github repository settings and make your repository *Public*.
- Paste your repo URL at [binder.org](https://mybinder.org/) and click **launch**. This will launch a temporary online Jupyter Lab server, but be mindful of the following:
  - Changes cannot be saved like in a regular Jupyter notebook: if you close the web browser tab, all changes will be lost.
  - However, you can still use git, which can serve as a way of saving your work (i.e. push frequently). You can do this as you would do from Jupyter Lab on your computer: open a terminal tab!
    - Note however that you will need to [configure your username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git#setting-your-git-username-for-every-repository-on-your-computer) and [email](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-email-address-for-every-repository-on-your-computer) like you would after a fresh install of git on your computer.
