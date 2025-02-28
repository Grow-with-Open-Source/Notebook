# Welcome to CONTRIBUTING.md

Hey there, fellow Developer !!!... We're happy to see and hyped about making your, *probably,* first contribution to this open-source repo. We heartily welcome you to your journey in open source contribution. We hope you have fun learning and teaching at the same time. For the **Notebook**, most of the contribution will be related to content writing like blogs, tips & tricks, tech updates, various documentation, etc.

## Setting up Environment

Before you even start working on your content writing, make sure you've got the right environment installed to build the project locally. As this project is based on Jekyll[^1] framework with Chirpy theme, you can refer to the [offical documentation by Chirpy theme](https://chirpy.cotes.page/posts/getting-started/ "goto chirpy-theme docs") or you can follow the following instruction which are derived from the official docs...

### For Windows:

The recommended way to setup environment for this project is through dev container, but you can also install all the dependecies natively if you want **(native installation is NOT recommended)**. 

#### Dev Container

To setup environment using **Dev Container**, follow the instruction

- Install Docker using [Docker Desktop](https://www.docker.com/products/docker-desktop/ "go download docker desktop").
- Download and Install [VS Code](https://code.visualstudio.com/ "go download vs code").
- Open VS Code and install [Dev Container extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers "go install dev-container extension") from the extensions tab.

Well that's it... You got the all the things are ready and all you gotta do is reopen the project file by clicking <kbd>Reopen in container</kbd>, just as shown below...

![Dev Container Demo](/assets/img/dev-container-demo.gif)

Dev container does all the heavy lifting for you and creates a container and setup the required environment for you. Now, you can write your blog within this dev container and then commit and push your changes though the shell of the container.

> [!NOTE]
> If you're doing this for the first time, it might take a while depending on your system specs. 

<details>
<summary><h4>Native Installation (Not Recommended)</h4></summary>
<div>

You can setup the required environment by installing dependencies manually. This is quite tedious process compare to [Dev Containers](#dev-container "goto dev container installation") method and it would be more difficult to debug the issue caused during installation *(if there was an issue during installation)*. With that being said, let's see how you setup required environment by natively installing dependencies...

> [!TIP]
> You can checkout [Jekyll Docs](https://jekyllrb.com/docs/installation/ "goto jekyll docs") for more details regarding installation.

- Start by downloading and installing the `Ruby` using [RubyInstaller](https://rubyinstaller.org/downloads/ "Download RubyInstaller"), and choose the latest one with Devkit with default options.

- Run `ridk install` on command prompt, If the installer doesn't prompt you the following image at the end of the installation...

<div align="center">

![prompt-img](/assets/img/contribute-to-notebook/cmd-prompt-img.png)

</div>

- Go ahead and select <kbd>MSYS2 and MINGW development toolchain</kbd> option by pressing `3` + <kbd>Enter</kbd>.

- Open a new command prompt window from the start menu, Use the following command to check whether `Ruby` has been properly installed and its `PATH` has been set properly.
```powershell
ruby -v
```

- Now use the following command to install `Jekyll` and `Bundler`:
```powershell
gem install jekyll bundler jekyll-theme-chirpy
```

- Use the following command to check whether the `bundler` and jekyll framework are installed properly or not.
```powershell
bundle info --path jekyll-theme-chirpy
```

- Now, your system is ready to build and use the project locally.


<div>
</details>


### For Unix-based system:

For all Unix-based system, native installation is more preferrable and recommended but you can still use [Dev Containers](#dev-container "goto dev container installation") if you want. In this section, we will discuss the native installation method...

> [!IMPORTANT]
> Install Jekyll environment based on distro-based installation specified in the [Jekyll Docs](https://jekyllrb.com/docs/installation/ "goto jekyll docs").

Just for sake of simplicity, we'll take a look at install in Ubuntu *(as it's widely used)*

- Run important updates using package manager.
```bash
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
```

- Install required dependecies using package manager.
```bash
sudo apt install ruby-full build-essential zlib1g-dev -y
```

> [!TIP]
> Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account.

- Adding required environmental variable.
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

- Let's verify if `ruby` is installed properly or not.
```bash
ruby -v
```

- Installing Jekyll frame along with Chirpy theme.
```bash
gem install jekyll bundler jekyll-theme-chirpy
```

- That's it, you have required environment for running the project locally.

### For MacOS:

If you're using MacOS, then you can either choose to go with [Dev Containers](#dev-container "goto dev container installation") or proceed with native installation. But since, MacOS is based upon Unix-based system, it's more preferrable to go for native installation. With that being said, let's see how we can setup environment in MacOS systems,

- Install Homebrew package manager. You can find more about Homebrew at [brew.sh](https://brew.sh "goto homebrew official page").
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> [!ALERT]
> If you're facing any issues while setting up the project in MacOS, check out the [Trobleshooting post](https://github.com/Grow-with-Open-Source/Notebook/discussions/3#discussioncomment-7151280) within the [Help Request](https://github.com/Grow-with-Open-Source/Notebook/discussions/3 "Goto Help Request Discussion") discussion.

- Install required dependecies
```bash
brew install chruby ruby-install
```

- Install the latest stable version of `Ruby` _(supported by Jekyll[^jekyll-offical-website])_:
```bash
ruby-install ruby 3.4.1
```

- Configuring shell to use `ruby`.
```bash
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc
source ~/.zshrc
```
> [!NOTE]
> If you're default shell is `bash`, then replace `.zshrc` with `.bash_profile` or `.bashrc`. If you’re not sure, read this external guide to [find out which shell you’re using](https://www.moncefbelyamani.com/which-shell-am-i-using-how-can-i-switch/ "find you shell").

- Check if `ruby` is installed properly or not.
```bash
ruby -v
```

- Installing Jekyll frame along with Chirpy theme.
```bash
gem install bundler jekyll jekyll-theme-chirpy
```

- Now, your system is ready to build and use the project locally.

## Build the project Locally

After setting up the environment, you can start contributing to the project:

- Start by [forking](https://github.com/Grow-with-Open-Source/Notebook/fork "let's fork the repo") the repository.

- Clone the forked repository to your local machine.
```bash
#cloning the repo
git clone https://github.com/<your-github-user-name>/Notebook.git

#entering the project directory
cd Notebook
```

- Use the following command to install project dependencies.
```bash
bundle
```

- Host the static website locally using the following command to preview the current state of the project.
```bash
bundle exec jekyll s
```

> [!NOTE]
> Use `--incremental` argument to update the project live while working on it...
```bash
bundler exec jekyll s --incremental
```

- If the project build is successful, then you can view the project build that is hosted through your [localhost:4000/Notebook](http://127.0.0.1:4000/Notebook/). Well done, you have successfully set up the project within your local system.

## Getting Started with Contribution

Now that you set up the environment required and started analyzing the project, you have to know a few things about the project structure and its configuration before you start working on your content writing.

### Instructions and Guidelines

- All of the content writing will be done in Markdown *(`.md`)* file format. So, Make yourself more comfortable with Markdown syntax through [Offical GitHub Documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github "visit the offical GitHub Docs").

- Since this open source is based chripy[^2] theme jekyll[^1] project, You're not limited by Markdown only. You can do much more using simple Markdown that provides easy writing while supporting limited HTML elements. Check out the Chirpy-based [post creation](https://chirpy.cotes.page/posts/write-a-new-post/) and [text and typography](https://chirpy.cotes.page/posts/text-and-typography/) posts to know more.

- You need to add your details to link the author's details with the posts. You can add your author details to the **`_data/authors.yml`** file in the following format:
```yaml
# Make sure the key_value is unique and not to be a duplicate
unique_key_value:
    name: <author_name>
    twitter: <twitter_id>
    url: <personal (or) contact url>
```

<details>
<summary>Looking for an example ?</summary>
<div>

```yml
shamith_watchdogs:
  name: Shamith Nakka
  twitter: shamith_nakka
  url: https://github.com/iamwatchdogs/
```

<div>
</details>

- It's recommended to use the images through CDN links. But if for some reason you are unable to do so, then store them in a new folder that is named after your post and save that folder within **`assets/img`** directory as **`assets/img/<your-project-name>/`**. Try avoid the process of *storing images within `assets/img` directory as it reflects the size of the project.

- Place your content writing files within the **`_posts`** directory, following the naming convention **`YYYY-MM-DD-file-name.md`**, e.g., `2023-09-27-welcome-to-notebook.md`. **Use lowercase letters and separate words with a single dash.**

- Each and every content writing file should contain the following `Front Matter` for the project to be successfully built:
```md
---
title: <title>
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [<main_categories>, <sub_categories_1>, ..., <sub_categories_n>]
tags: [<tag_1>, ..., <tag_n>]
author: <respective_author_key_value>
media_subpath: "/assets/img/<your_img_directory_name>" <!--(or) respective CDN link -->
image:
  path: <name_of_the_img_for_page_cover>
  alt: <alternative_text>
---

# Your content writing begins here
```

<details>
<summary>Looking for an example ?</summary>
<div>

```md
---
title: Welcome to the Notebook
date: 2023-09-21 20:34:00 +0530
categories: [Welcome, Guide]
tags: [introduction]
author: shamith_watchdogs
media_subpath: "/assets/img/welcome-page"
image:
  path: "welcome-img.jpg"
  alt: "Welcome Page"
---
```

<div>
</details>

> [!IMPORTANT]
> - Note that the `+/-TTTT` in the `date` section refers the **UTC offset**. You can find your **UTC offset** value by searching for your country in the [list of UTC](https://en.wikipedia.org/wiki/List_of_UTC_offsets "Goto List of UTC offsets"). And if you're from India, you can use the above UTC offset from the example.
> - If there is more than one person/author working on a single post, then use `authors` attribute instead of `author`. Also, the input for the `authors` attribute will be a list of unique_key_value representing the authors.
> - It's complete optional to have `media_subpath` and `image` attribute. Use them if and only if, your post requires any images.
> - If your post is using images, then you can make use of `media_subpath` to reduce the redundant path. But specify the path, you can use only the name of image to place it on your blog instead of giving whole path which would be redundant.
> - The `image` attribute will act as the page cover or thumbnail for your post. It's up to you to add a page-cover or not. Note that if you specified a path using `media_subpath`, then you can specify the image name used for page-cover without of full path.

These are important instructions and guidelines you need to follow to create a successful post without any issues.

### Contributing

Now that you have a basic understanding of the workings of the project, let's talk a bit about the process of contributing...

**Step 1:** You start you setting up the environment [*(as discussed above)*](#setting-up-environment).

**Step 2:** After setting up the required environment, now build the project locally [*(as discussed above)*](#build-the-project-locally).

**Step 3:** Create a new branch to work on your contribution. use the following command:
```bash
# create and check out to new branch
git checkout -b <simple-relavent-branch-name>

# check your branch currently in
git branch
```

**Step 4:** Now that you got the project up and running within your local machine, start by adding your details as an author to [`_data/authors.yml`](_data/authors.yml) file as [mention above](#instructions-and-guidelines). Make sure your author key is unique and different from others.

**Step 5:** Now go ahead and create a new markdown file to work on post to contribute. Make sure you follow the naming convention for the file which is `YYYY-MM-DD-your-post-name`. And you post name should be all small alphanumeric separated by dashs *(-)*.

**Step 6:** Make sure you commit every change now, one commit for adding the author name and one for creating a new markdown file. Using the following command:
```bash
# Adding or staging the changes
git add .

# commiting the changes
git commit -m "<related-short-message>"
```

> [!IMPORTANT]
> Make sure to commit your each and every change with proper description

- **Step 7:** After creating the empty markdown file, add the required metadata *(or)* configuration as [mention above](#instructions-and-guidelines).

- **Step 8:** Now, proceed with your content writing using markdown syntax and also using additional features of Chirpy theme[^2].

- **Step 9:** If you have any images, try adding CDN links to the source containing all the images. If not, you can create a new directory using your posts name *(separated with dashes -)* within the `assets/img/` as `assets/img/<your-post-name>`. And also mention the CDN or directory path in `media_subpath` attribute as [mention above](#instructions-and-guidelines).

- **Step 10 (optional):** After you are done with your post *(don't forget to come with each and every change)*, if you want you can add a page-cover (or) thumbnail to your post. Just mention the image name within the sub-attribute `path` of the main attribute `image`.

- **Step 11:** After committing all the changes and completion of your work. push your commit to your forked repo, using the following commands:
```bash
# check your branch name
git branch

# push your commit to origin repo
git push origin <your-branch-name>
```

- **Step 12:** Now, create a pull request to the [original repo](https://github.com/Grow-with-Open-Source/Notebook). [Learn about Pull requests](https://docs.github.com/articles/using-pull-requests "offical GitHub documentaiton")

And that is it, you have done it !!!... Now, it's time for the maintainer to review your work and merge your pull request. If there's any issue with your pull request, then the maintainer will contact you and ask for a few changes. And he merges your Pull request, you have successfully made your first open-source contribution that actually helps others.

Everybody can see your work and make use of it. Good job, mate !!...

## Rules and Regulations

Here are some ground rules that you need to follow:

- It's important for you to commit to each and every change. Don't just finish all of your work with a single commit. If you're a newbie, it will only be tolerated 3 times.
- Sending several pull requests for a single post is not accepted.
- Your Pull Request will not be merged, if you have modified, changed, or deleted any files or content that doesn't belong to you.
- Pull Request containing any illegal, NFSW or any other content which doesn't help others in any way possible will be closed immediately.
- The Pull Request will only be merged if everything seems to be in order. You be notified if you did something wrong, and your pull request will only be merged if the notified changes are made.


[^1]: **GitHub's Jekyll Framework official Page:** <https://jekyllrb.com>
[^2]: **Chirpy Jekyll theme's Offical Repo:** <https://github.com/cotes2020/jekyll-theme-chirpy>
