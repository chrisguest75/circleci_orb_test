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
