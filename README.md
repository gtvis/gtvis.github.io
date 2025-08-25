<img src="assets/images/logo_gold.png" alt="Georgia Tech Visualization Lab"/>

Website for the Georgia Tech Visualization Lab, deployed at <https://vis.gatech.edu>

### Setup and Run

- Install [Jekyll and dependencies](https://jekyllrb.com/docs/).
   - For Windows users: we recommend installing Ruby@3.1.4 (https://rubyinstaller.org/downloads/) to avoid the dependency problem between Jekyll and Ruby (For more information: https://talk.jekyllrb.com/t/liquid-4-0-3-tainted/7946).
   - On OSX, you may need also need to downgrade ruby, e.g., ``rvm reinstall 3.1.4 --with-openssl-dir=`brew --prefix openssl@1.1` --with-opt-dir=`brew --prefix openssl@1.1``
`
- Install [Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) (tested on node v18, npm v10).
- Install npm-based packages using `npm install`.
- Install bundles: `bundle install`.
- Compile and serve the app using `bundle exec jekyll serve --livereload`.
- Open browser to <http://localhost:4000>.

### To add/modify/remove content, follow the READMEs in the corresponding directories

- [Group](_groups)
- [Faculty](_faculty)
- [Student](_students)
- [Course](_courses)
- [Publication](_publications)
- [News, Gallery, Sponsor, or Showcase item](_data)

### Steps to make edits

If you are unfamiliar with forking and submitting pull requests,
[here is a 4-minute guide](https://guides.github.com/activities/forking/) to get you started.

1. Fork this repository.
2. Make your edits on the `main` branch of the forked repository and commit them.
3. Submit a Pull Request on the original (non-forked) repository, from your forked repository's `main` branch to the
   original repository's `main` branch, and an admin will merge it.


### Deployment
** Only for an admin **

1. For each successful _push_ to the `main` branch, Github will automatically start a workflow (via Github Actions) and compile the source into the `build` branch. If something is going wrong here or if something needs to be changed here, edit [.github/workflows/github-pages.yml](.github/workflows/github-pages.yml).
2. Verify the build through a green checkmark next to the commit message / workflow AND by actually going to the `build` branch to see fresh commits (sometimes, the workflow does not automatically push these commits, which is weird.). Depending on what goes wrong, either `Re-run all jobs` or debug your code by following the error log.
3. To deploy the code in the `build` branch to vis.gatech.edu, first login to the GT VPN.
4. Go to hosting.gatech.edu > My Plesk Hosting > vis.gatech.edu (you must be an admin to see these -- reach out to core faculty if you must.)
5. Under 'My Sites' click on `vis.gatech.edu`.
6. Under Dev Tools' click on `Git` > `Pull now` 
7. Verify by opening vis.gatech.edu in a browser (in cognito window to be absolutely sure).
8. All set!

### Contact

- gtvislab \[at\] gmail \[dot\] com
