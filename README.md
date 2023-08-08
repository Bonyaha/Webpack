1. Start the application with the command `npm start` in development mode.
2. In development mode, the application fetches notes from the address `http://localhost:3001/notes`.
3. The production version, bundled with the command `npm run build`, uses the address `https://notes2023.fly.dev/api/notes` to retrieve the list of notes.
4. To inspect the bundled production version locally, navigate to the build directory and execute the command `npx static-server`.
5. The `BACKEND_URL` variable in the `App.js` file is a global constant that receives a different value based on the environment it's being bundled for. This value is taken from the `webpack.config.js` file using the following configuration:

   ```javascript
   plugins: [
     new webpack.DefinePlugin({
       BACKEND_URL: JSON.stringify(backend_url)
     })
   ]

if the application is started with the command npm start in development mode, it fetches the notes from the address http://localhost:3001/notes. The version bundled with the command npm run build uses the address https://notes2023.fly.dev/api/notes to get the list of notes.
We can inspect the bundled production version of the application locally by executing the following command in the build directory:npx static-server
The BACKEND_URL variable in App.js file is a global constant,that gets a different value depending on the environment that the code is being bundled for. It is taken from webpack.config.js file: plugins: [
			new webpack.DefinePlugin({
				BACKEND_URL: JSON.stringify(backend_url)
			})
		]