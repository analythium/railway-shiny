# Deploy Shiny Apps to Railway.app

## What is Railway

> Infrastructure, Instantly
>
> Develop code in a cloud that feels local. When you're ready, deploy from anywhere

<https://railway.app/>

## Setup

Following the Railway.io docs: <https://docs.railway.app/>

**Step 1.** Install `railway` CLI <https://docs.railway.app/cli/installation>

**Step 2.** Sign up or sign in and go to your dashboard <https://railway.app/dashboard> (you can sign up with email or with your GitHub account)

You might have to _verify_ your account (promise not to do anything fishy)

**Step 3.** Log in with `railway login` and follow the prompts

**Step 4.** Create a new project

**4a** Option 1: In your dashboard, create a new _Empty Project_

You'll be presented with a project ID, e.g. `a4dd399d-494e-4b2f-944a-ebc05be245df`

Link to this project using CLI (copy from dashboard settings)

```bash
export ID="a4dd399d-494e-4b2f-944a-ebc05be245df"
railway link $ID
```

**4b** Option 2: use CLI, select _Empty Project_

```bash
railway init
```

**Step 5.** Add your project to the folder

If you have a Dockerfile in your project directory, you can just run `railway run` with no arguments to build and run the Dockerfile.

As in Heroku, you need the `PORT` variable: <https://docs.railway.app/deployment/up>

You'll see something like:

```bash
🎉 Built railway-local/hot-rainstorm-production:latest
🚂 Running at 127.0.0.1:4411
```

Follow the link and test the app. Ctrl+C to kill.

**Step 6.** Deploy your app:

```bash
railway up
```

The assigned `*.up.railway.app` domain times out instantly: <https://feedback.railway.app/bug-reports/p/websocket-issue>

Custom domain is supposed to work <https://docs.railway.app/deployment/custom-domains>

**Step 7.** Custom domain

1. Select the environment and enter your domain name
2. Add the `CNAME` record to the DNS settings for your domain
3. Wait for Railway to verify your `CNAME` record

Once a custom domain has been correctly configured, Railway will automatically generate and apply a Let's Encrypt certificate.

This is still failing...

## Todo

- See how to link to GitHub
- Pricing info

> #### Starter Plan Project Limits
>
> Stater plans are designed to help you evaluate Railway and are fit for hobbyist projects. You get access to all features on Railway and you have no limits to the amount of projects you can provision.
>
> Starter plans get $5 of credits that do not accumulate.
