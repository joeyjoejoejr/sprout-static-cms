# sprout-static-cms

A [sprout](http://github.com/carrot/sprout) template for creating a static CMS in Roots using Contentful and Netlify. Please go through the setup steps before running the template.

### Installation

- `npm install sprout -g`
- `sprout add static-cms https://github.com/carrot/sprout-static-cms.git`

### Setup

You should sign up for a Contentful and Netlify account before using this template as you will need an access token for both to complete the template configuration.

You will need the following set up before you run this:

#### A Contentful account and "space"

1. Create an account on their [website](https://contentful.com/).
2. Click on the top right menu and create a new space for your project (or edit the default one you start with).
3. Switch to the space and click on the gear on the top menu to go to Space Settings
4. Note your Contentful Space ID, you'll need this for the template

#### A Contentful API token

1. Go to your project's space
2. Click on 'API' on the top menu bar
3. Click on 'API Keys' under the 'Content Delivery API' section on the left hand bar
4. Add a new API by clicking 'Add API key' and fill out the form
5. Note the Production API Access Token, you'll need this for the template.

#### A Netlify account and API token

1. Create an account on their [website](https://www.netlify.com/)
2. Log in and click on your account dropdown at the top right and select `OAuth apps`
3. Under Personal Access Tokens, create a new token.
4. Note your Netlify API token, you'll need this for the template.

### Generators

Once your static CMS project is set up, this template will also give you useful generators. These generators rely on `contentful.coffee` in order to provide the credentials needed to interact with Contentful, **do not move this file if you need to use a generator**.

#### Model Generator

Sprout-static-cms comes equipped with a Contentful Content Model generator. Pass in the Content Model's name followed by a list of fields to generate following a `name:type` format, for example:

```bash
sprout run static-cms model Post title:text description:text slug:symbol date:date rank:integer price:number private:boolean
``` 

If you don't specify a field type, sprout will default to a text field.


#### Tests

In order to run the tests, you'll need to add a couple environment variables. This project is setup to use [dotenv](https://github.com/motdotla/dotenv), so all you should need to do is add a `.env` file with the following variables:

```
DELIVERY_TOKEN=XXXXXXXXXXXX
MANAGEMENT_TOKEN=XXXXXXXXXXXX
SPACE_ID=XXXXXXXXXXXX
```

You should use a test Contentful account (i.e. not in use in production) to populate these values.

### Options

- **name** (name of template)
- **description** (a short description of the template)
- **space_id** (the ID for the Contentful space associated with this project)
- **delivery_token** (your Contentful space's Delivery API token)
- **management_token** (your Contentful account's Management API token)
- **netlify_token** (your Netlify account's personal access token)
