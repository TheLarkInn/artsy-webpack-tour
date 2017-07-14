# artsy-webpack-tour
Annotations on webpack source code in a pseudo-guided fashion.

## Just an Experiment
My goal as one of the maintainers for [webpack](https://github.com/webpack/webpack) is being able to help developers better understand how webpack works. 

Demystify the tool so it helps you become more comfortable understanding how to use it and contributing to our source code and supporting packages.

## Have a question? 
The whole goal is to teach you how to use webpack, therefore please ask questions about the annotations you see inside of a github issue, and I will help you clarify any parts of what is seen below. There is **NO wrong question**. 

## Disclaimer: This may not match master!
I will likely not keep this up to date with every change in master on webpack/webpack. Rather, the purpose is to teach how to read and view the flow of the compilation lifecycle through webpack.

##Text Transcripts
To make this searchable, the text of each image has been transcribed into the "transcripts" section. The title of each transcript anchors to the respective image. 

### Help Wanted ❤😍💕❤😍💕❤😍💕❤😍💕❤😍

### Version (webpack 2.2.1+ from master)


![Step 1](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative01.png)
![Step 2](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative02.png)
![Step 3](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative03.png)
![Step 4](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative04.png)
![Step 5](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative05.png)
![Step 6](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative06.png)
![Step 7](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler01.png)
![Step 8](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler02.png)
![Step 9](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler03.png)
![Step 10](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler04.png)
![Step 11](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler05.png)
![Step 12](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler06.png)
![Step 13](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler07.png)
![Step 14](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler08.png)
![Step 15](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler09.png)
![Step 16](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf01.png)
![Step 17](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf02.png)
![Step 18](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf03.png)
![Step 19](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf04.png)
![Step 20](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf05.png)
![Step 21](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf06.png)
![Step 22](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf07.png)
![Step 23](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf08.png)
![Step 24](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf09.png)
![Step 25](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf10.png)
![Step 26](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf11.png)
![Step 27](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf12.png)
![Step 28](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compilation-seal01.png)

### Text Transcript

#### <a name="Step 1">WebpackOptionsApply.js (List of plugins) </a>
"All plugins for options cases"
"These handle any module format"

#### <a name="Step 2"> WebpackOptionsApply.js (Explanation of Options) </a>
"getting opts from config"
"options target code"
"ES5 OOP (class W0A(?) extends 0A)"
"records"
"never used this before ¯\\_(ツ)_/¯ "
"plugin system makes for extremely flexible feature development"

#### <a name="Step 3">WebpackOptionsApply.js (Native modules) </a>
"Certain targets ship w/ other modules native to their deploy target like Electron"
"Similar to electron man but instead the "client" side. Thus diff externals"

####<a name="Step 4">WebpackOptionsApply.js (Source Map Flavors)</a>
"handling bad target values"
"all of this logic is for the 'devtool' prop. Allows for about 15-20 flavors of source maps"
"That was Sean's first ever PR!!!"

####<a name="Step 5">WebpackOptionsApply.js (More module madness!)</a>
"1. Single plugin for entry prop that is registered then"
"2. Executes via subsequent event"
"these plugins are grouped b/c they are all for module interop"
"these plugins all pertain to general optimizations including tree shaking"
"performance budgets code"
"in version 1, you had to do this yourself, now in v2 we handle it"
