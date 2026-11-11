# Read a Repository's History

Goal

To clone a public repo and use git to answer questions relating to its history. I had to answer how many commits it had, three most frequent authors, what the first commit contained, which files changed in latest commit and discuss commit messages shown.

The repo which I used was:

https://github.com/alan2207/bulletproof-react.git

Steps Taken
Firstly I found an open-source repo to clone. I then ran specific commands in order to answer the goal questions mentioned above. After I had ran all of the commands and received an output for each, I reviewed over the information returned.

From this, I was able to determine the following information:

One commit message I would copy: 777534a Remove head component in discussion route because it's already used in ContentLayout
I think that this commit message is very descriptive and allows you to know exactly what was changed.
One commit message I would improve: 1fb422b update
This commit message gives no real information other than an update. Anyone reviewing this would need to go into the commit file changes directly to work out what has happened. 

Commands

git clone https://github.com/alan2207/bulletproof-react.git
git rev-list --count HEAD
git shortlog -sn | head -3
git log --reverse --stat | head -40
git show --stat HEAD
git log --oneline

Results

rachel@Mac bulletproof-react % git rev-list --count HEAD
271
rachel@Mac bulletproof-react % git shortlog -sn | head -3
   116  Alan Alickovic
    84  Alan
     3  Gabriel Romay
rachel@Mac bulletproof-react % git log --reverse --stat | head -40
commit cfd9e62f50bc011883245da52fc4db0ae6a8cf18
Author: Alan <alan2207@live.com>
Date:   Sun May 30 12:45:57 2021 +0200

    Initialize project using Create React App

 .gitignore             |    23 +
 README.md              |    46 +
 package.json           |    43 +
 public/favicon.ico     |   Bin 0 -> 3870 bytes
 public/index.html      |    43 +
 public/logo192.png     |   Bin 0 -> 5347 bytes
 public/logo512.png     |   Bin 0 -> 9664 bytes
 public/manifest.json   |    25 +
 public/robots.txt      |     3 +
 src/App.css            |    38 +
 src/App.test.tsx       |     9 +
 src/App.tsx            |    26 +
 src/index.css          |    13 +
 src/index.tsx          |    17 +
 src/logo.svg           |     1 +
 src/react-app-env.d.ts |     1 +
 src/reportWebVitals.ts |    15 +
 src/setupTests.ts      |     5 +
 tsconfig.json          |    26 +
 yarn.lock              | 11447 +++++++++++++++++++++++++++++++++++++++++++++++
 20 files changed, 11781 insertions(+)

commit aec85662e55bbe75e2c3403dd36ea65f29ada055
Author: Alan <alan2207@live.com>
Date:   Sun May 30 16:47:42 2021 +0200

    initial commit

 .env.example                           |    3 +
 .eslintrc.js                           |   73 ++
 .prettierrc                            |    7 +
 .vscode/extensions.json                |    9 +
 .vscode/settings.json                  |    6 +
 craco.config.js                        |   13 +
rachel@Mac bulletproof-react % git show --stat HEAD
commit 9506629ed003a561c6627735480cce4994244bb4 (HEAD -> master, origin/master, origin/HEAD)
Author: Alan Alickovic <alan2207@live.com>
Date:   Thu May 14 15:53:03 2026 +0200
9506629 (HEAD -> master, origin/master, origin/HEAD) Add 'Building Bulletproof React Components' resource
79710eb Upgrade @playwright/test and its dependencies to fix CI (#259)
c1dce3f Include Base UI in headless components list (#258)
73ad892 add logo (#173)
dde5a4a docs: Add comprehensive AGENTS.md for AI coding agents (#245)
e426d53 Remove duplicate paragraph in security.md - fixes #191Remove duplicate paragraph in security.md - fixes #191Update security.md (#243)
c66ea06 Update README.md
49c4249 Correct spelling in security.md (#236)
21189c3 docs: fix grammatical error in Update security.md (#224)
4da36db Upgrade to react router 7 - lib mode (#227)
a55e984 Update auth.tsx (#226)
1deca0b docs: Correct link references and adjust indentation (#223)
5cdc208 Rename directory from "test" to "testing" (#221)
74ff903 Next app router improvements (#222)
9010f0d Improvements (#220)
e6acf0a feat(dropdown): add demo implementation for Dropdown component (#212)
5e5bdfe Fix Markdown formatting of `project-structure.md` file (#213)
6ad9ffb fixed typo with package name. should be using react-router-dom (#211)
10f330f Add nextjs app and pages version of the app (#198)
ea1ebba docs: fix typo in Security section (#199)
5d1c7e5 add pagination (#196)
af48f06 Improvements (#194)
701820e Address Vite warnings in build step (#193)
c0f0568 updated instructions to change directory (#190)
5d4cbbb add data prefetching (#189)
1508d6d move the sample app to apps subfolder (#187)
7ca3bb8 Merge pull request #182 from julianty/patch-1
5a4ecbf Update project-structure.md
dfd2950 Merge pull request #178 from michaeltg17/fixRandomTimeoutsInDiscussionsTest
1b4b0f8 Merge pull request #179 from michaeltg17/removeUneededHeadUsageInDiscussionRoute
5ecd1d1 Merge pull request #175 from alan2207/standalone-mock-server
8ef3fa3 run standalone mock server in e2e tests
e19da4d add standalone mock server
777534a Remove head component in discussion route because it's already used in ContentLayout
40b8c99 Add timeouts to "should create, render and delete discussions" test
e8181b4 Merge pull request #162 from frontEnd-fucker/feature-filename-check
0ec4251 fix folder naming convention
d8cb1f3 Merge pull request #169 from alan2207/fix-docs-links
09bd95e fix docs links
ef999b0 Merge pull request #168 from alan2207/fix-prod-build
6a0c15d Fix prod build
c4933b9 add folder name convention
s-broken-url-state-example-code-url
3df3472 Merge pull request #164 from drsnowflake/patch-2
1f344d0 Update testing.md
0f016a2 update state management url state example code url
580640e fix filename
65b365f support filename check
05992c4 Merge pull request #160 from alan2207/dev
47d4255 update docs
9aecaf6 use react router loaders to fetch data before rendering
866de72 update docs
03e1c29 enforce unidirectional codebase
undaries)
rrel files
2b6a228 simulate network delay in mocks
fc23c32 Merge pull request #158 from marktoh/fix-typo
505840b Merge pull request #157 from f440/fix-invalid-link
349caf6 fix(docs/security.md): fix typo
1f2fafe fix(docs/security.md): fix typo
6887b9a fix(~/README.md): fix typo
5b59a5c Fix broken link in documentation
17ad2a7 Merge pull request #152 from alan2207/dev
1fb422b update
b898a0d update docs
9f57a2b better usage of query options
7fe5817 fix app file case
51dd805 improve api hooks
76065e9 refactor playwright tests
9a62bf1 prefer mutate over mutateAsync
513d8bd skip ci when only docs change have been made
7ddd5c4 improve query keys
60d95a3 update docs
d7e71d7 more generic api client
49c5092 update formatting rules
proof-react/pull/144
oof-react/pull/113
c8cd689 improve testing setup
9411b74 improve type inference and api input validation
3c3d455 use kebab case for all files
a1cfae7 prefer types over interfaces
1679821 switch to shadcn ui and update components
be8f370 restructure routes
4046a41 prevent circular dependencies
e74349e store the auth token in a cookie instead of localStorage
74c7612 validate env variables
0658e52 update zustand mocks for testing
af4bfcf update license
977a77e update react-query-auth
ugin-prettier
eact/pull/153
4243e83 update docs
d5d4355 upgrade rest of dependencies
dd427db update pipeline
31aeb1b tests working
45fba58 migrate to modern stack - almost fully working
a3aff53 show author for discussion and comment
e-management-links
e14092b update state-management.md and performance.md links
d0cae77 Merge pull request #146 from W01fw00d/patch-1
fddd12c Update state-management.md
fe3b0f7 Update state-management.md
5c59489 Update state-management.md useState and useReducer links
ction
706137f Merge pull request #138 from thibaut-decherit/docs/typo
5736800 docs: typo
9fa4021 docs: typos
efcdf68 docs: typo
11d9149 Merge pull request #123 from madhusudan-kulkarni/patch-1
0a9616e Update additional-resources.md
dc6f7b1 Merge pull request #103 from sarahsga/jest-cmd
7744d52 Merge pull request #105 from ARehmanMahi/readme_patch
989d0bb Docs - extend performance section
bbc26e8 Reviewed grammatical errors in README.md
cb02c1e fix test script
2facb64 Update project-structure.md
0a0e8bd cleanup api
9468e1a fix styles
3f213d0 Merge pull request #73 from dc7290/feature/plop-generator-types
96fbe16 Added type declarations
ent-in-feature
15d13d1 Merge pull request #71 from johnny-miyake/remove_unused_import
93ef2e2 Merge pull request #70 from caocuong2404/master
497076a Merge pull request #68 from pfcodes/patch-1
03a79d4 Remove unused import in smoke.ts
cd0b86b fix: the`initMocks` function always starts
db7c46d Update project-structure.md
190bf9d feat(generator): generage component in feature
f3b2be7 Merge pull request #62 from theodorosploumis/patch-1
bbb8068 Add new URL for pagespeed
32ed545 update react-query and fix typings
8d4c3fb Merge pull request #57 from nikhilkutinha/master
02ae36c Remove redundant import
ff8308f Merge pull request #54 from sinchang-codespaces/fix-license
a980556 Fix license badge
20a2d8d Update additional-resources.md
1b1d5de Merge pull request #51 from neighborhood999/chore/docs
fbea925 docs(state-management): add xstate
721e39d docs: remove redundant words and update code block
84caeb3 Update components-and-styling.md
226e590 remove unused code
1ae780b Merge pull request #50 from fishmandev/patch-2
1e167ad Update components-and-styling.md
4173e87 Merge pull request #49 from fishmandev/patch-1
2ada63b Update api-layer.md
fad8976 update docs link
f641f55 Merge pull request #45 from TeXmeijin/master
a5b5acd Merge pull request #46 from miily8310s/fix/react-document-link
352fbe1 Merge pull request #44 from yegorgunko/patch-1
2e18d8a fix/react-document-link react link to en page
283ef20 chore: uninstall react-helmet and install react-helmet-async
81c7e38 chore: typo & code indent small fixes
dbbcee2 Merge pull request #38 from ebof1223/patch-1
014f5bc Update style-guide.md
8af48d5 Update style-guide.md
3ce3b92 Merge pull request #37 from omarefg/hf/fixServerCacheStateUrls
943dbbb Added missing server cache state urls
3232d14 Merge pull request #36 from pfcodes/patch-1
a560cf5 Merge pull request #35 from jnorris441/patch-1
9d7223a Update state-management.md
2225376 change useUpdateDiscussion to useUpdateTeam
11f069d Merge pull request #34 from oliviertassinari/patch-1
ada4358 Material-UI is now MUI
712c9c9 change integration test example link
de77fed update docs and minor fixes
63bf000 fix logo on auth screens
-await-keyword
f2cdba3 remove redundant await keyword
0ac22fc Update additional-resources.md
3e11202 update docs
6f8fdd7 fix test query
mple-link
age
b79d764 Merge pull request #29 from cassler/bug/notifications-sb-title
a527462 fix flaky cypress test
49894fc Fix error boundary link
24c59b7 Fix some typos
087be4c Fix "Notifications" typo on Storybook meta
d4cfbed fix app provider import in storybook
0a3ff58 Merge pull request #25 from ryota-murakami/patch-1
7320440 [README] add Github Actions Status Badge
9b60738 Merge pull request #19 from ryota-murakami/add/github-action
2deeed0 deploy demo app
add834f refactor api, stores, providers, routes
8571892 minor updates
c32e2d8 add github-action CI
c1080bc Merge pull request #18 from nina1012/master
f5ea160 links fix
f6e7e8d Merge pull request #14 from nanzm/master
c7d01d1 Add no match route
0c27235 fix: admin cannot delete user comment (#8)
6f7d873 cleanup unused stuff
a5b1b40 Merge pull request #6 from ryota-murakami/add-getstart-command
647b1b4 docs: replace install commands and update description
0f9be5f docs: add get start command
45bf607 Merge pull request #5 from nina1012/fixing-typos
eb7e1bc fixing typos in docs
063704b Merge pull request #4 from na-ji/patch-1
87fdc4d fix some typos in README
d009429 Merge pull request #3 from colmtuite/patch-1
f78eab7 typos
fb2a267 update docs
7c5a3da fix api mocking check
2b95ebb update docs
9e4eb2c cleanup
341919f add and show createdAt property
d6c0a09 update docs
550a881 update docs
7caa7bd update authorization
717190a update docs
c6c9a01 update docs
d7b4b5f update docs
c88fa69 update docs
27a5c5a update docs
90f2c19 update docs
1b39470 update docs
4dd2427 make rbac more flexible with policies
3682cea e2e test update
59a1b22 update e2e generic data
1d31ab5 add e2e test with cypress
d85179b update components
a6e4baf upgrade storybook
885fcbf update tests
d02a6bc test discussions
def4503 update code coverage config
a72545c add code coverage and testing lint plugins
c6a0a1d more components tests
083cf49 better validation and error handling
ff7d5af add more tests
38913d0 test form component
a3fa1ec test setup and cleanup
9143989 replace interfaces with type aliases
31dfcc8 test notification store
9143adc test useDisclosure hook
5e6f413 upgrade react-query-auth
5510dad fix Form default schema type
a13560f add head tags via react-helmet
899c847 form validation with zod
347802c maintainence fixes
9818ed5 better global error handling
6dd37a6 update structure
b64176d add missing notifications
b0c38f2 husky working
8f12f45 test
ba7f7e2 husky setup
c88625a complete all required user stories
a5e309b improve storybook
ca4117e add notifications system with zustand
85b1c59 add custom useDisclosure hook
f3bf517 storybook setup
f471c91 set authorization
4f96205 update docs
50545d8 readme and licence
5c56691 add users
85e2463 view discussion, create and list comments
4631591 consistent modern react importing
d3f79e7 more ui improvements
870c7f6 add optimistic updates for create and delete discussions
e2edc23 refactor components
824888c read, create, delete discussions
749f03d delay mocked server responses
8128490 forms
d33a465 better data hooks types
6e197ac add api layer
048fb96 update readme
4ac8414 update
c441eca updates
00bd3f0 data modelling
f88bf5e more setup
aec8566 initial commit
cfd9e62 Initialize project using Create React App
~

rachel@Mac bulletproof-react % git log --oneline
9506629 (HEAD -> master, origin/master, origin/HEAD) Add 'Building Bulletproof React Components' resource
79710eb Upgrade @playwright/test and its dependencies to fix CI (#259)
c1dce3f Include Base UI in headless components list (#258)
73ad892 add logo (#173)
dde5a4a docs: Add comprehensive AGENTS.md for AI coding agents (#245)
e426d53 Remove duplicate paragraph in security.md - fixes #191Remove duplicate paragraph in security.md - fixes #191Update security.md (#243)
c66ea06 Update README.md
49c4249 Correct spelling in security.md (#236)
21189c3 docs: fix grammatical error in Update security.md (#224)
4da36db Upgrade to react router 7 - lib mode (#227)
a55e984 Update auth.tsx (#226)
1deca0b docs: Correct link references and adjust indentation (#223)
5cdc208 Rename directory from "test" to "testing" (#221)
74ff903 Next app router improvements (#222)
9010f0d Improvements (#220)
e6acf0a feat(dropdown): add demo implementation for Dropdown component (#212)
5e5bdfe Fix Markdown formatting of `project-structure.md` file (#213)
6ad9ffb fixed typo with package name. should be using react-router-dom (#211)
10f330f Add nextjs app and pages version of the app (#198)
ea1ebba docs: fix typo in Security section (#199)
5d1c7e5 add pagination (#196)
af48f06 Improvements (#194)
701820e Address Vite warnings in build step (#193)
c0f0568 updated instructions to change directory (#190)
5d4cbbb add data prefetching (#189)
1508d6d move the sample app to apps subfolder (#187)
7ca3bb8 Merge pull request #182 from julianty/patch-1
5a4ecbf Update project-structure.md
dfd2950 Merge pull request #178 from michaeltg17/fixRandomTimeoutsInDiscussionsTest
1b4b0f8 Merge pull request #179 from michaeltg17/removeUneededHeadUsageInDiscussionRoute
5ecd1d1 Merge pull request #175 from alan2207/standalone-mock-server
8ef3fa3 run standalone mock server in e2e tests
e19da4d add standalone mock server
777534a Remove head component in discussion route because it's already used in ContentLayout
40b8c99 Add timeouts to "should create, render and delete discussions" test
e8181b4 Merge pull request #162 from frontEnd-fucker/feature-filename-check
0ec4251 fix folder naming convention
d8cb1f3 Merge pull request #169 from alan2207/fix-docs-links
09bd95e fix docs links
ef999b0 Merge pull request #168 from alan2207/fix-prod-build

Observations
N/A
