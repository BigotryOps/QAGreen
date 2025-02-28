---
title: Create ABAPDoc Comments in Your Class in ABAP Environment QA Green changed
description: Learn how to maintain ABAPDoc documentation for your class in SAP Business Technology Platform (BTP), ABAP Environment so your comments appear in the Outline view.
auto_validation: true
time: 10
tags: [ tutorial>beginner, software-product>sap-btp--abap-environment, software-product>sap-business-technology-platform ]
primary_tag: programming-tool>abap-development
---

## Prerequisites
- You have an entitlement to SAP BTP ABAP Environment. For more information, see **Tutorial**: [Create Your First ABAP Console Application](abap-environment-console-application), steps 1-2
- You have installed [ABAP Development Tools](https://tools.hana.ondemand.com/#abap), latest version

## Details
### You will learn  
- How to maintain ABAPDoc comments
- How to synchronize comments so they appear in the Outline View
- How to add an sorted list
- How to create a link to other development object documentation within ADT

ABAPDoc comments are used to document your code. This makes it more readable. If other developers use one of your development objects, they can find out more about it by selecting the object name in the code and choosing **Element Info ( `F2` )**.

All ABAPDoc comments begin with **`"!`**.

Always replace `XXX` with your initials or group number.

---

[ACCORDION-BEGIN [Step 1: ](Open ABAP class)]
First, open the ABAP class **`ZCL_AMDP_DEMO_XXX`** from the tutorial [Create an AMDP and Analyze Its Performance](abap-environment-amdp-profiling)

!![Image depicting step-1-open-class](step-1-open-class.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 2: ](Create ABAPDoc comment)]
1. Immediately before the class definition, add an ABAPDoc comment to the class by entering **`"!`** and choosing **Auto-complete ( `Ctrl+Space` )**.

2. From the dropdown list, choose **Paragraph**, then add the following comment:

    **`"!<p>Class tests AMDP</p>`**

    !![step2a-choose-paragraph](step2a-choose-paragraph.png)

    >You must insert the ABAPDoc comment **immediately** before the declaration; otherwise you will get a warning from ADT.

3. Add the following to the paragraph ( `<p>` ) tag: **`class="shorttext synchronized"`**, so your code looks like this:

    ```
    "!<p class="shorttext synchronized">Class tests AMDP: </p>
    ```

4. Add the following comments to the table type **`ty_result_line`** and to the method **`GET_FLIGHTS`** respectively:

    ```
    "!<p class="shorttext synchronized">Table type of Flights from HANA DB</p>
    "! <p class="shorttext synchronized"> Method reads flights from HANA DB using AMDP</p>
    ```

5. Save and activate your class.

The comments should now appear in the Outline View:

!![step2b-shorttext-synch-class](step2b-shorttext-synch-class.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 3: ](Add sorted list)]
1. Choose **Enter**. The system automatically inserts the ABAPDoc comments annotation `"!"` for you.

2. Again, choose **Auto-complete ( `Ctrl+Space` )**. Then choose **Sorted list**.

    !![step3a-add-sorted-list](step3a-add-sorted-list.png)

3. Add the following two statements, so that your code looks like this:

 ```Shell [2,5,7,10,12]
    sed "s/const HtmlWebpackPlugin = require('html-webpack-plugin');/const HtmlWebpackPlugin = require('html-webpack-plugin');const CopyWebpackPlugin = require('copy-webpack-plugin');/g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    sed "s/new HtmlWebpackPlugin(/new CopyWebpackPlugin([\
    {context: 'public', to: 'index.html', from: 'index.html'  },\
    {context: 'node_modules\/@luigi-project\/core',to: '.\/luigi-core',from: {glob: '**',dot: true}}],\
    {ignore: ['.gitkeep', '**\/.DS_Store', '**\/Thumbs.db'],debug: 'warning'\
    }),\
    new HtmlWebpackPlugin(/g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    sed "s/template: paths.appHtml,/template: paths.appHtml,\
    filename: 'sampleapp.html',/g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    sed "s/public\/index.html/public\/sampleapp.html/g" config/paths.js > config/paths.tmp.js && mv config/paths.tmp.js config/paths.js

    sed "s/publicUrl + '\/index.html',/publicUrl + '\/sampleapp.html',/g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    sed "s/const isWsl = require('is-wsl');//g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    #This can throw a warning, it can be ignored
    sed "s/!isWsl/true/g" config/webpack.config.js > config/webpack.config.tmp.js && mv config/webpack.config.tmp.js config/webpack.config.js

    echo "const path = require('path');
    module.exports = {
        entry: './src/luigi-config/luigi-config.es6.js',
        output: {
            filename: 'luigi-config.js',
            path: path.resolve(__dirname, 'public'),
        },
    };">webpack.config.js

    sed 's/"scripts": {/"scripts": {\
    \    "buildConfig":"webpack --config webpack.config.js",/1' package.json > p.tmp.json && mv p.tmp.json package.json

    echo '{
        "globals": {
            "Luigi": "readonly"
        }
    }'>.eslintrc.json
    ```

[DONE]
[ACCORDION-END]


### More Information
- SAP Help Portal: [Editing ABAP Doc Comments](https://help.sap.com/viewer/5371047f1273405bb46725a417f95433/Cloud/en-US/4ec136586e391014adc9fffe4e204223.html)
- SAP Keyword Documentation: [ABAPDoc](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendoccomment.htm)

---
