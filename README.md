# gatsby-source-marketo-forms

Plugin to fetch forms data from marketo platform and create a gatsby data query

## Install
  `npm install gatsby-source-marketo-forms`

  `yarn add gatsby-source-marketo-forms`


## How to use
  You'll need to create credentials for the marketo API. All instruction how to create those keys you will find in this link ->
  http://developers.marketo.com/rest-api/authentication/


### Setup
  Go to `gatsby-config` and add the following lines to the config
  ```
  {
    resolve: 'gatsby-source-marketo',
    options: {
      munchkinId: '<MUNCHKIN_ID_KEY>',
      clientId: 'CLIENT_ID_KEY',
      clientSecret: CLIENT_SECRET_KEY'
    }
  }
  ```

  And that's it. To explore your marketo forms data go to -> `/__graphql`

  Sample of query
  ```
  query MarketoQuery {
    allMarketoForm {
      edges {
        node {
          marketoId
          marketoChildren {
            dataType
            hintText
            id
            label
          }
        }
      }
    }
  }
  ```

 And a tip for the end. If you wanna use this to avoid AdBlock issue you can use this URL -> `https://<YOUR MARKETO SPACE ID>.mktoedge.com/index.php/leadCapture/save2`  to send form data instead of `http://app-<YOUR MARKETO SPACE ID>.marketo.com/index.php/leadCapture/save` because AdBlock is blocking requests which having some words in URL like `marketo`

 `app-<YOUR MARKETO SPACE ID>.marketo.com` is a wrapper for `<YOUR MARKETO SPACE ID>.mktoedge.com` so it's works exactly this same


