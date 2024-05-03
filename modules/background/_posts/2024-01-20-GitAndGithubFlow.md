---
Git, Github and Github flow
---

# The moving parts of a version-controlled training website

The system described here has X key components:

1. A source repository to which authors contribute training materials

2. A static site generator that builds a website from that source 

3. A hosting service that serves the website to the world

## Version control for training materials

As previously described, static site generators take content in the form of text and associated images and, using a template, create web pages. The text that underlies these web pages is typically written in a markup language like Markdown. The advantage of using a text-based system for building content is that content is easy to reuse and easy to track using version control.

Version control systems like git track changes in files using "diffs" that record which lines have changed, been added or removed. The popular Github website provides a hosting service for "git repositories" which are collections of files (typically small files like text and images) managed by the git version control system.

Each set of changes in a git repository is called a commit. These commits each have associated descriptions that can state what is involved in the change. Github manages a system of permissions involving whether repositories are public or private and who has permission to view and make changes.

## How the site is built

Services like [Github Pages](https://pages.github.com/) and [Netlify](http://netlify.com/) offer different options for invoking the static site generation code to build the website from the source materials. Github Pages uses [Jekyll](https://jekyllrb.com/) configured with a certain set of default plugins. Github Pages reads the source, typically in the `gh-pages` branch of the repository, and builds a website from it.

Netlify uses Docker containers to invoke the "build script" that is in the source repository. This means that while Netlify is more complex to set up than Github Pages but offers more flexibility. With Netlify one can use Jekyll plugins that are not included in the Github Pages default configuration, or one can use an entirely different system for building the website, for example, the [Hugo](https://gohugo.io/) static site builder (or even dynamic sites, which are outside the scope of this discussion).

## Hosting static site content

Both Github Pages and Netlify have certain "free plans" that allow serving web pages at no cost. The [limits on use of Github Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#limits-on-use-of-github-pages) include a prohibition on commercial activity, and size and usage restrictions: no sites larger than 1 GB, and a bandwidth limit of 100 GB per month.

Netlify's [Starter plan](https://www.netlify.com/pricing/) also offers 100 GB of bandwidth per month and a limited set of features compared to their paid plans.

These limits are typically more than enough to host a training website.

# Making changes with Github Flow

As described above, the source material for a training website is stored in a git repository and changes are managed using git. The techniques for collaborating on a git repository on Github are known as [Github Flow](https://docs.github.com/en/get-started/using-github/github-flow). The key elements of Github Flow are:

1. Never directly change the main branch (in our discussion, the `gh-pages` branch) of the repository

2. Use branches (either in the main website repository or in a [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)) to make changes.

3. Contribute the changes back to the main branch using a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).


