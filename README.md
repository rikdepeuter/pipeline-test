Release pipeline flow:

1. main: determine version, build, push images to aws, create branch "releases/{version}/tst"
2. releases/{version}/tst: deploy, create branch "releases/{version}/stg"
3. releases/{version}/stg: wait for approval, deploy, create branch "releases/{version}/prd"
4. releases/{version}/prd: wait for approval, deploy, create branch "releases/{version}/acc"
5. releases/{version}/acc: deploy

trigger "releases/*" on created/updated
