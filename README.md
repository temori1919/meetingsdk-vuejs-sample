# Zoom Meeting SDK Vue.js sample

Use of this sample app is subject to our [Terms of Use](https://explore.zoom.us/en/legal/zoom-api-license-and-tou/).

---

**NOTE:** This sample app has been updated to use [Meeting SDK app type](https://developers.zoom.us/docs/meeting-sdk/create/) credentials instead of [JWT app type](https://developers.zoom.us/docs/platform/build/jwt-app/) type credentials.

---

This repo is a [Vue.js 2](https://vuejs.org/) app generated via the [Vue CLI](https://cli.vuejs.org/) that uses the [Zoom Meeting SDK](https://developers.zoom.us/docs/meeting-sdk/web/) to start and join Zoom meetings and webinars.

![Zoom Meeting SDK Client View](/public/images/meetingsdk-web-client-view.gif)

## Installation

To get started, clone the repo:

`$ git clone https://github.com/zoom/meetingsdk-sample-vuejs.git`

> To setup and run the app you will need [Yarn](https://yarnpkg.com/getting-started).

## Setup

1. Once cloned, navigate to the `meetingsdk-sample-vuejs` directory:

   `$ cd meetingsdk-sample-vuejs`

1. Then install the dependencies:

   `$ yarn install`

1. Open the `meetingsdk-sample-vuejs` directory in your code editor.

1. Open the `src/components/HelloWorld.vue` file, and enter values for the variables:

   **NEW:** To use the [Component View](https://developers.zoom.us/docs/meeting-sdk/web/component-view/), replace `HelloWorld.vue` with `HelloWorldNew.vue`. (The `leaveUrl` is not needed). Also, uncomment the Component View CSS tags and comment out the Client View CSS in `public/index.html`.

   | Variable                   | Description |
   | -----------------------|-------------|
   | authEndpoint          | Required, your Meeting SDK auth endpoint that secuerly generates a Meeting SDK JWT. [Get a Meeting SDK auth endpoint here.](https://github.com/zoom/meetingsdk-sample-signature-node.js) |
   | sdkKey                   | Required, your Zoom Meeting SDK Key or Client ID for Meeting SDK app type's created after February 11, 2023. [You can get yours here](https://developers.zoom.us/docs/meeting-sdk/developer-accounts/#get-meeting-sdk-credentials). |
   | meetingNumber                   | Required, the Zoom Meeting or webinar number. |
   | passWord                   | Optional, meeting password. Leave as empty string if the meeting does not require a password. |
   | role                   | Required, `0` to specify participant, `1` to specify host. |
   | userName                   | Required, a name for the user joining / starting the meeting / webinar. |
   | userEmail                   | Required for Webinar, optional for Meeting, required for meeting and webinar if [registration is required](https://support.zoom.us/hc/en-us/articles/360054446052-Managing-meeting-and-webinar-registration). The email of the user starting or joining the meeting / webinar. |
   | registrantToken            | Required if your [meeting](https://developers.zoom.us/docs/meeting-sdk/web/client-view/meetings/#join-meeting-with-registration-required) or [webinar](https://developers.zoom.us/docs/meeting-sdk/web/client-view/webinars/#join-webinar-with-registration-required) requires [registration](https://support.zoom.us/hc/en-us/articles/360054446052-Managing-meeting-and-webinar-registration). |
   | zakToken            | Required to start meetings or webinars on external Zoom user's behalf, the [authorized Zoom user's ZAK token](https://developers.zoom.us/docs/meeting-sdk/auth/#start-meetings-and-webinars-with-a-zoom-users-zak-token). |
   | leaveUrl                   | Required for Client View, the url the user is taken to once the meeting is over. |

   Example:

   ```js
   authEndpoint: "http://localhost:4000",
   sdkKey: "abc123",
   meetingNumber: "123456789",
   passWord: "",
   role: 0,
   userName: "Vue.js",
   userEmail: "",
   registrantToken: "",
   zakToken: "",
   leaveUrl: "http://localhost:8080"
   ```

1. Save `HelloWorld.vue`.

1. Run the app:

   `$ yarn serve`

## Usage

1. Navigate to http://localhost:8080 and click "Join Meeting".

   ### Client View

   ![Zoom Meeting SDK Client View](/public/images/meetingsdk-web-client-view.gif)

   ### Component View

   ![Zoom Meeting SDK Component View](/public/images/meetingsdk-web-component-view.gif)

   Learn more about [Gallery View requirements](https://developers.zoom.us/docs/meeting-sdk/web/gallery-view/) and [see more product screenshots](https://developers.zoom.us/docs/meeting-sdk/web/gallery-view/#how-views-look-with-and-without-sharedarraybuffer).

## Deployment

The Vue.js Sample App can be easily deployed to [GitHub Pages](#github-pages), or [another static web hosting service](#other-static-web-hosting), like an AWS S3 bucket.

### GitHub Pages

1. Create a repo on [GitHub](https://github.com).

1. Add the remote to your project:

   `$ git remote add origin GITHUB_URL/GITHUB_USERNAME/GITHUB_REPO_NAME.git`

1. Open the `vue.config.js` file and on line 3 replace `/GITHUB_REPO_NAME/` with your GitHub repo name surrounded by slashes like this: `/GITHUB_REPO_NAME/`.

1. Build your project:

   `$ yarn build`

1. Rename the `dist` folder to `docs`

1. Git add, commit, and push your project:

   `$ git add -A`

   `$ git commit -m "deploying to github"`

   `$ git push origin master`

1. On GitHub, in your repo, navigate to the "settings" page, scroll down to the "GitHub Pages" section, and choose the "master branch /docs folder" for the source.

1. Now your project will be deployed to https://GITHUB_USERNAME.github.io/GITHUB_REPO_NAME.

### Other Static Web Hosting

1. Build your project:

   `$ yarn build`

1. Deploy the complied `/dist` directory to a static web hosting service, like an AWS S3 bucket.

### Advanced Deployment

For more advanced instructions on deployment, [see the Vue.js Deployment docs](https://cli.vuejs.org/guide/deployment.html).

## Need help?

If you're looking for help, try [Developer Support](https://devsupport.zoom.us) or our [Developer Forum](https://devforum.zoom.us). Priority support is also available with [Premier Developer Support](https://explore.zoom.us/docs/en-us/developer-support-plans.html) plans.
