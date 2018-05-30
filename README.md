# scss-demo
在 SCSS 里使用 PX2REM(Windows下不需要安装ruby)
```
npm config set registry https://registry.npm.taobao.org/
touch ~/.bashrc
echo 'export SASS_BINARY_SITE="https://npm.taobao.org/mirrors/node-sass"' >> ~/.bashrc
source ~/.bashrc
npm i -g node-sass
mkdir ~/Desktop/scss-demo
cd ~/Desktop/scss-demo
mkdir scss css
touch scss/style.scss
start scss/style.scss
node-sass -wr scss -o css
```
编辑 scss 文件就会自动得到 css 文件

在 scss 文件里添加
```
@function px( $px ){
  @return $px/$designWidth*10 + rem;
}

$designWidth : 640; // 640 是设计稿的宽度，你要根据设计稿的宽度填写。如果设计师的设计稿宽度不统一，就杀死设计师，换个新的。

.child{
  width: px(320);
  height: px(160);
  margin: px(40) px(40);
  border: 1px solid red;
  float: left;
  font-size: 1.2em;
}
```
即可实现 px 自动变 rem