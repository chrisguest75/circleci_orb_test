# Instructions 

## Guides
FOLLOWING THESE INSTRUCTION:
* [orb-development-kit](https://circleci.com/docs/2.0/orb-author/#orb-development-kit)
* [orb-author-validate-publish](https://circleci.com/docs/2.0/orb-author-validate-publish/)
* [writing-inline-orbs](https://circleci.com/docs/2.0/reusing-config/#writing-inline-orbs)



https://github.com/chrisguest75/circleci_orb_test

## Steps 
```sh
# run the setup for the circle ci cmdline
circleci setup
# you'll have to create an api key and add it to the config
https://circleci.com/account/api
nano /Users/cguest/.circleci/cli.yml
```

```sh
# create a namespace for the org
circleci namespace create chrisguest75 github chrisguest75
```

```sh
# create a template orb
circleci orb init circleci_orb_test  
```

```sh
circleci orb create chrisguest75/circleci_orb_test  
circleci orb validate src/@orb.yml
circleci orb publish src/@orb.yml chrisguest75/circleci_orb_test@dev:first
```

The default template assumes `alpha` is tag it is looking for. 

git checkout -b publish_test   

Commit message is detailed in default [README.md](./README.md)
"My first rev of the orb [semver:0.0.1]"

You have to edit the merge message.
Note: Merge pull request #1 from chrisguest75/publish_test.

git commit --amend   
Merge pull request #1 from chrisguest75/publish_test [semver:patch]

circleci orb list --uncertified | grep guest
chrisguest75/circleci_orb_test (0.0.1)

https://circleci.com/developer/orbs/orb/chrisguest75/circleci_orb_test



Usage:
```yaml
orbs:
    circleci_orb_test: chrisguest75/circleci_orb_test@0.0.1

commands:
  test:               
    steps:
      - circleci_orb_test/greet:
          to: "this is a test"

```