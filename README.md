#gatsby-source-marketo-forms

Plugin for fetch forms data from marketo platform and create a gatsby graphql query

## Install
  `yarn add gatsby-source-marketo-forms`

## How to use
  You need to create credentials to marketo API
  http://developers.marketo.com/rest-api/authentication/


  Add in `gatsby-config` the following lines
  ```
  {
    resolve: 'gatsby-source-marketo',
    options: {
      munchkinId: '--',
      clientId: '---',
      clientSecret: '---'
    }
  }
  ```

  And you should be ready to use forms data as a graphql query
  ```
  query MyQuery {
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


