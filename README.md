# vigilant-guacamole
To delete all the files in a folder on Node.js, you can use the `fs.readdir()` method to get a list of all the files in the folder, and then use the `fs.unlink()` method to delete each file.
Here is an example: 
const fs = require('fs');
// Get a list of all the files in the folder.
const files = fs.readdirSync('my-folder');
// Delete each file.
for (const file of files) {
  fs.unlinkSync(`my-folder/${file}`);
}
This code will delete all the files in the `my-folder` folder.
Note that the `fs.unlink()` method will throw an error if the file does not exist. If you want to ignore errors, you can use the `fs.unlinkSync()` method.
You can also use the `glob` module to get a list of all the files in a folder. The `glob` module provides a number of methods for matching files and directories. For example, the following code will get a list of all the files in the `my-folder` folder that end with the `.txt` extension:
const glob = require('glob');
// Get a list of all the files in the folder that end with the `.txt` extension.
const files = glob.sync('my-folder/**/*.txt');
// Delete each file.
for (const file of files) {
  fs.unlinkSync(file);
}
This code will delete all the files in the `my-folder` folder that end with the `.txt` extension.
Note that the `glob` module will only match files that exist. If you try to match a file that does not exist, you will get an error.
