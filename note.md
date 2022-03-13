# make some notes

### Steps

### initial repo

    mkdir learn-husky && cd learn-husky
    npm/yarn init --yes
    git init
    #touch .gitignore
    #config .gitignore
    echo {}> .prettierrc.json
    #touch & config .prettierignore
    #touch .eslintrc.json with eslint command
    npx eslint --init
### Install

    npm/yarn -D prettier eslint husky lint-sta

### RUN SOME COMMANDS

    npx prettier --check .
    npx prettier --write .
    npx eslint --fix .
