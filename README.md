# melcma.nodejs

Ubuntu 16.04 and Ubuntu 18.04 supported

Define application list to install local npm modules:

    applications:
      myapp.com:
        npm: true
        start: bin/www
        port: 8001

Define global npm packages to install:

    npmGlobalPackages:
      - pm2
      - create-react-app
      - nodemon
      - npm-check-updates

You will also need to put global and local git config files:

Pass extra variables when importing this playbook:

    - import_tasks: roles/melcma.nodejs/main.yml
      vars:
        - version: 10
        - packages: "{{ npmGlobalPackages }}"