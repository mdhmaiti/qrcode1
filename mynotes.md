# qr code generator project.
    This is a simple documentation of the project.This is a easy way to create a qr code generator.
## objectives 
     
  1. Use the inquirer npm package to get user input.
  2. Use the qr-image npm package to turn the user entered URL into a QR code image.
  3. Create a txt file to save the user input using the native fs node module.
  
### details 
1. ```import inquirer from "inquirer";``` This is the starting point of the node js . This is silmilar to the require that we use in the node js. But to use this you have to add ```"type": "module", ``` in the package. json file.
2. Inquirer allows you to define validation rules for user input. You can specify conditions or constraints that the user's input must meet, such as minimum/maximum length, allowed characters, or specific formats. Inquirer provides error handling capabilities to display custom error messages when the input doesn't meet the defined criteria.In the code i have used the default inquirer format that is given in the document you can just search it in the npm.
3. ```import qr from "qr-image";``` this is the main thing that is responsible for the generation of the qr code image .
``` js
    var qr_svg = qr.image(url);
    qr_svg.pipe(fs.createWriteStream("qr_img.png"));

```
4. Now we want to create a text file , for this we can simply use the fs .

 ```js
    import { writeFile } from 'node:fs';
import { Buffer } from 'node:buffer';

const data = new Uint8Array(Buffer.from('Hello Node.js'));
writeFile('message.txt', data, (err) => {
  if (err) throw err;
  console.log('The file has been saved!');
});
 ```
