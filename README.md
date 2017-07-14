# artsy-webpack-tour
Annotations on webpack source code in a pseudo-guided fashion.

## Just an Experiment
My goal as one of the maintainers for [webpack](https://github.com/webpack/webpack) is being able to help developers better understand how webpack works. 

Demystify the tool so it helps you become more comfortable understanding how to use it and contributing to our source code and supporting packages.

## Have a question? 
The whole goal is to teach you how to use webpack, therefore please ask questions about the annotations you see inside of a github issue, and I will help you clarify any parts of what is seen below. There is **NO wrong question**. 

## Disclaimer: This may not match master!
I will likely not keep this up to date with every change in master on webpack/webpack. Rather, the purpose is to teach how to read and view the flow of the compilation lifecycle through webpack.

## Text Transcripts
To make this searchable, the text of each image has been transcribed into the "transcripts" section. The title of each transcript anchors to the respective image. 

### Help Wanted ❤😍💕❤😍💕❤😍💕❤😍💕❤😍

### Version (webpack 2.2.1+ from master)


<a name="Step1"></a>!
[Step 1](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative01.png)
<a name="Step2">![Step 2](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative02.png)</a>
<a name="Step3">![Step 3](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative03.png)</a>
<a name="Step4">![Step 4](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative04.png)</a>
<a name="Step5">![Step 5](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative05.png)</a>
<a name="Step6">![Step 6](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative06.png)</a>
<a name="Step7">![Step 7](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler01.png)</a>
<a name="Step8">![Step 8](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler02.png)</a>
<a name="Step9">![Step 9](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler03.png)</a>
<a name="Step10">![Step 10](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler04.png)</a>
<a name="Step11">![Step 11](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler05.png)</a>
<a name="Step12">![Step 12](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler06.png)</a>
<a name="Step13">![Step 13](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler07.png)</a>
<a name="Step14">![Step 14](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler08.png)</a>
<a name="Step15">![Step 15](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compiler09.png)</a>
<a name="Step16">![Step 16](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf01.png)</a>
<a name="Step17">![Step 17](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf02.png)</a>
<a name="Step18">![Step 18](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf03.png)</a>
<a name="Step19">![Step 19](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf04.png)</a>
<a name="Step20">![Step 20](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf05.png)</a>
<a name="Step21">![Step 21](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf06.png)</a>
<a name="Step22">![Step 22](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf07.png)</a>
<a name="Step23">![Step 23](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf08.png)</a>
<a name="Step24">![Step 24](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf09.png)</a>
<a name="Step25">![Step 25](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf10.png)</a>
<a name="Step26">![Step 26](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf11.png)</a>
<a name="Step27">![Step 27](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-nmf12.png)</a>
<a name="Step28">![Step 28](https://github.com/TheLarkInn/artsy-webpack-tour/blob/master/images/webpack-narrative-compilation-seal01.png)</a>

## Text Transcript

### [WebpackOptionsApply.js (List of plugins)]("Step1") 
"All plugins for options cases"
"These handle any module format"

### [WebpackOptionsApply.js (Explanation of Options)]("Step2") 
"getting opts from config"
"options target code"
"ES5 OOP (class W0A(?) extends 0A)"
"records"
"never used this before ¯\\_(ツ)_/¯ "
"plugin system makes for extremely flexible feature development"

### [WebpackOptionsApply.js (Native modules)]("Step3")
"Certain targets ship w/ other modules native to their deploy target like Electron"
"Similar to electron man but instead the "client" side. Thus diff externals"

### [WebpackOptionsApply.js (Source Map Flavors)]("Step4")
"handling bad target values"
"all of this logic is for the 'devtool' prop. Allows for about 15-20 flavors of source maps"
"That was Sean's first ever PR!!!"

### [WebpackOptionsApply.js (More module madness!)]("Step5")
"1. Single plugin for entry prop that is registered then"
"2. Executes via subsequent event"
"these plugins are grouped b/c they are all for module interop"
"these plugins all pertain to general optimizations including tree shaking"
"performance budgets code"
"in version 1, you had to do this yourself, now in v2 we handle it"
