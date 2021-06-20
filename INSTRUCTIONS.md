https://circleci.com/docs/2.0/orb-author-validate-publish/
https://circleci.com/docs/2.0/reusing-config/#writing-inline-orbs
https://github.com/chrisguest75/circleci_orb_test

FOLLOWING THESE INSTRUCTION:
https://circleci.com/docs/2.0/orb-author/#orb-development-kit

circleci setup
https://circleci.com/account/api
nano /Users/cguest/.circleci/cli.yml
circleci namespace create chrisguest75 github chrisguest75
circleci orb create chrisguest75/circleci_orb_test  
circleci orb init circleci_orb_test  
circleci orb validate src/@orb.yml
circleci orb publish src/@orb.yml chrisguest75/circleci_orb_test@dev:first


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
