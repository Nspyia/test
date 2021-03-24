# README

This README would normally document whatever steps are necessary to get your application up and running.

## Deploy in AWS

1. Accesse into our AWS server

   ```bash
   ssh -i ~/.ssh/wonderland.pem root@ec2-13-56-19-255.us-west-1.compute.amazonaws.com
   ```

2. Use nixos-rebuild to build the flake supported git repo.

   ```bash
   nixos-rebuild switch --flake git+ssh://git@bitbucket.org/jzrw/deployhub?rev=06cf88863930a7366e8545c6da06b75dbfe7e9d9#wonderpool
   ```

   Building in local(not AWS) you need to replace `#wonderpool` as ` #wonderpool-local `

   Alternatively, you can use the wonder deployment tools to simplify the `nixos-rebuild ...` command
   
   
   

## Wonder deployment tools

Wonder deployment tools is a build tool that makes it easy to build this project on a cloud server.

## Example for using

- Get help

  ```
  depl
  ```

- Build latest

  `depl build_latest`

  Optional parameters:  `--branch=master --machine=wonderpool`

  The following examples are equivalent:

  ```
  depl build_latest
  depl build_latest master
  depl build_latest --branch=master
  depl build_latest master wonderpool
  depl build_latest --branch=master --machine=wonderpool
  ```

- Build

  `depl build`

  Required parameters: `--commit_id`

  Optional parameters:  `--machine=wonderpool`

  

  ```
  depl build d2d06b30221af62dc8aab1a72653e5d520b1cb35
  depl build d2d06b30221af62dc8aab1a72653e5d520b1cb35 wonderpool
  ```

- Query this repo recent commit id

  `depl recent`

  Optional parameters:  `--branch=master`

  

  ```
  depl recent
  depl recent master
  ```

- Pull

  Note: If there is a new commit, be sure to run  `depl pull`  before running all following command to ensure that this repo of the server(which you want build) is up to date

  ```
  depl pull
  ```

  
  

