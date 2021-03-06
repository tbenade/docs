## Environment variables

What if you have an API key you need during a deploy or during a build? This is
information that is either unique for each server you want to deploy to or may be
too sensitive to store in the repository. Wercker supports a number of ways to
store and expose this data as environment variables.

### Global environment variables

There are variables which are `global`. These are available during builds and deploys.
Typically, these are used to store API tokens for after-steps such as hipchat, campfire etc.
These variables are called pipeline variables and can be set in the settings tab
of your application.

[Read more on creating env vars &rsaquo;](/docs/environment-variables/creating-env-vars.html)

### Deploy environment variables

The second set of variables are specific to `deploy targets`, and can only be set
directly on the deploy target. Typically, these are used to store information
such as `hostnames`, `ssh-keys`, `passwords` and more.
These variables are called `deploy target variables`.

### Available environment variables

You can also use a [script step](/learn/steps/introduction.html) and use the export
command to see the full list of all variables at that moment during the build/deploy.
This is convenient since there are reasons why the environment variables step does
not show all environment variables available during the pipeline run.

[See the complete list of available env vars &rsaquo;](/docs/environment-variables/available-env-vars.html)

If you want to know which environment variables are available during a build or
deploy, look at the environment variables step of your pipeline run.

```yaml
- script:
    code: |
        export
```


