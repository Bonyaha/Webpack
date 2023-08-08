if the application is started with the command npm start in development mode, it fetches the notes from the address http://localhost:3001/notes. The version bundled with the command npm run build uses the address https://notes2023.fly.dev/api/notes to get the list of notes.
We can inspect the bundled production version of the application locally by executing the following command in the build directory:npx static-server
The BACKEND_URL variable in App.js file is a global constant,that gets a different value depending on the environment that the code is being bundled for. It is taken from webpack.config.js file: plugins: [
			new webpack.DefinePlugin({
				BACKEND_URL: JSON.stringify(backend_url)
			})
		]