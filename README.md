Travis CI status
StellarTerm ecosystem - client | api | directory
This StellarTerm monorepo consists of multiple projects built for the Stellar network including a trading client. The projects are in this monorepo to enable faster development speed.

Web Client
StellarTerm is a web based trading client for use on the Stellar network. This client aims to make it easy and safe for users of any skill level to trade on the Stellar network by making a clear and secure user interface. Try it out at https://stellarterm.com

API for developers (built on AWS Lambda)
The StellarTerm API contains information on the markets on the Stellar network. This information is useful for the StellarTerm client itself as well as other developers that want to use this data.

The API uses the Serverless framework for deployment to AWS Lambda. The API data is hosted on AWS S3 for high availability.

It is currently under active development and is not yet finished. See it in action here: https://api.stellarterm.com/

Directory
StellarTerm maintains a manually curated directory file with a listing of well known anchors and assets on the Stellar network. For more information, see the directory README.

StellarTerm client custom network
Testnet
To use the testnet, simply add #testnet to the url to activate it. To exit, refresh the page where the url is not #testnet.

Custom horizon builds
Some developers may want to use StellarTerm pointed to a custom horizon server or even a custom network. To do this, you must build StellarTerm locally.

The StellarTerm build process checks for the presence of relevant environment variables.

export STELLARTERM_CUSTOM_HORIZON_URL="https://horizon-testnet.stellar.org"
export STELLARTERM_CUSTOM_NETWORK_PASSPHRASE="Test SDF Network ; September 2015"
Once built, the configuration will be embedded into the StellarTerm output file (and the environment variable is no longer needed). To check this, look at the output of index.html and search for stCustomConfig.

Deployment
The project is hosted on GitHub pages in the stellarterm/stellarterm.github.io repository. The client is wrapped into a single html file and it's sha 256 sum is recorded on each git commit.

Client development instructions
Prerequisites
Make sure you have Node.js 7.4.0 or higher installed. If not, install it (Node version manager is recommended).

# Check your node version using this command
node --version
Environment Setup
# Clone the project
git clone https://github.com/stellarterm/stellarterm.git
cd stellarterm

# Install the npm and bower dependencies
npm run setup
Development mode
The build process has tools watches the code and rebuilds if something has changed. It will also serve the app locally (usually http://localhost:3000) and automatically refresh the page when changes are built.

npm start
Production build
This builds a single index.html file with assets inlined. The single file contains the whole app and can be hosted online. Output file is in ./dist/index.html.

npm run production
License
Products in the StellarTerm ecosystem is open source software and is licensed under the Apache-2.0 license. Please understand the license carefully before using StellarTerm.

Credits
Started the project using the super helpful react-gulp-browserify yeoman generator
