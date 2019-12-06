# Quick Start Guide

Get Strapi up and running in **less than 5 minutes** 🚀.

(Before you start, check that [Node.js and npm are properly installed](install-requirements.md) on your machine. Install the latest [Yarn v1.2.0 and package](https://yarnpkg.com/en/).)

<div class="video-container">
<iframe width="853" height="480" src="https://www.youtube.com/embed/4m1wKzzfs-M" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

_For a step-by-step guide, look at the [detailed tutorial](quick-start-tutorial.md)._



## 1. Install Strapi and Create a new project

:::: tabs

::: tab yarn

```bash
yarn create strapi-app my-project --quickstart
```

:::

::: tab npx

```bash
npx create-strapi-app my-project --quickstart
```

:::

::::

## 2. Create an Administrator user

Navigate to [**http://localhost:1337/admin**](http://localhost:1337/admin).

- Complete the form to create the first **Administrative** user profile.
- Click **Ready to start**.

## 3. Create a Restaurant Content Type

Navigate to [**PLUGINS** - **Content Type Builder**](http://localhost:1337/admin/plugins/content-type-builder), in the left-hand menu.

- Click the **"+ Add Content Type"** link.
- Enter `restaurant`, and click **Done**
- A window opens with fields options:
  - Click the **String** field
  - Enter `name` in the **Name** field
  - Click the **ADVANCED SETTINGS** tab, and check the `Required field` and the `Unique field`
  - Click the **"+ Add New Field"** button
  - Click the **Rich Text** field
  - Enter `description` under the **BASE SETTINGS** tab, in the **Name** field
  - Click **Done**
- Click the **Save** button and wait for Strapi to restart

## 4. Create a Category Content type

Navigate to [**PLUGINS** - **Content Type Builder**](http://localhost:1337/admin/plugins/content-type-builder), in the left-hand menu.

- Click the **"+ Add Content Type"** link
- Enter `category`, and click **Done**
- A window opens with fields options:
  - Click the **String** field
  - Enter `name` under the **BASE SETTINGS** tab, in the **Name** field
  - Click the **ADVANCED SETTINGS** tab, and check the `Required field` and the `Unique field`
  - Click the **"+ Add New Field"** button
  - Click the **Relation** field
  - On the right side, click the **Permissions** list and select, `Restaurant`
  - In the center, click the icon that represents `many-to-many`. The text must read, `Categories has and belongs to many Restaurants`
  - Click **Done**
- Click the **Save** button and wait for Strapi to restart

## 5. Add content to "Restaurant" Content Type

Navigate to [**CONTENT TYPES** - **Restaurants**](http://localhost:1337/admin/plugins/content-manager/restaurant?source=content-manager), in the left-hand menu.

- Click the **+ Add New Restaurant** button. Type `Biscotte Restaurant` in the **Restaurant** field. 
- Enter a description such as, `Welcome to Biscotte restaurant! Restaurant Biscotte offers a cuisine based on fresh, quality products, often local, organic when possible, and always produced by passionate producers.` into the **Description** field.
- Click **Save**.

Your restaurant is now listed in the entries.

## 6. Add categories to the "Category" Content Type

Navigate to [**CONTENT TYPES** - **Categories**](http://localhost:1337/admin/plugins/content-manager/category?source=content-manager).

- Click the **+ Add New Category** button. 
- Enter `French Food` in the **Category** field. 
- Select `Biscotte Restaurant`, from **Restaurant (0)** on the right-hand side.
- Click **Save**.

The **French Food** category is now listed in the entries.

- Click the **+ Add New Category** button. Enter `Brunch` in the **Category** field. **DO NOT ADD IT HERE** to `Biscotte Restaurant`.
- Click **Save**.

The **Brunch** category is listed in the entries.

Navigate to [**CONTENT TYPES** - **Restaurants**](http://localhost:1337/admin/plugins/content-manager/restaurant?source=content-manager).

- Click `Biscotte Restaurant`
- On the right, under **Categories(1)**, select the `Add an item...`, link and add **Brunch** as a category for this restaurant, and click the **Save** button.

You have now seen **two different ways** to use the **relation** field type to add and connect relations between Content Types.

## 7. Set Roles and Permissions

Navigate to [**PLUGINS** - **Roles & Permissions**](http://localhost:1337/admin/plugins/users-permissions/roles).

- Click the **Public** Role.
- Scroll to **Permissions**, find **Restaurant**. Select **find** and **findone** checkboxes.
- Repeat and find **Category**. Select **find** and **findone** checkboxes.
- Click **Save**.

## 8. Use the Content Type API in your application

Here we are! The list of **restaurants** is accessible at [`http://localhost:1337/restaurants`](http://localhost:1337/restaurants).

::: tip CONGRATULATIONS
👏 Congratulations, you have now completed the **Strapi Quick Start**. Where to go next?

- Learn how to use Strapi with React ([Gatsby](https://blog.strapi.io/building-a-static-website-using-gatsby-and-strapi) or [Next.js](https://blog.strapi.io/strapi-next-setup/)) or Vue.js ([Nuxt.js](https://blog.strapi.io/cooking-a-deliveroo-clone-with-nuxt-vue-js-graphql-strapi-and-stripe-setup-part-1-7/)).
- Read the **concepts** and do the [Tutorial](quick-start-tutorial.md) to deep dive into Strapi.
- Get help on [StackOverflow](https://stackoverflow.com/questions/tagged/strapi).
- Read the [source code](https://github.com/strapi/strapi), [contribute](https://github.com/strapi/strapi/blob/master/CONTRIBUTING.md) or [give a star](https://github.com/strapi/strapi) on GitHub.
- Follow us on [Twitter](https://twitter.com/strapijs) to get the latest news.
- [Join the vibrant and active Strapi community](https://slack.strapi.io) on Slack.
  :::
