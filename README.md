# Installation
## 1.ติดตั้ง library เข้ามาใน Project 
  npm i react-native-image-slider-box\
  หรือ\
  yarn add react-native-image-slider-box
## 2.(ทางเลือก) : ถ้าต้องการใช้ image library จากที่อื่น เช่น FastImage เป็นต้น\
  npm i react-native-fast-image\
  หรือ\
  yarn add react-native-fast-image

# วิธีการใช้

import React, {Component} from 'react';

import {StyleSheet, Text, View} from 'react-native';

//ทำการ import react-native-image-slide
import {SliderBox} from 'react-native-image-slider-box';

export default class App extends Component {

  constructor(props) {
  
    super(props);
    this.state = {
      //เก็บรูปไว้ใน state สามารถเก็บได้ทั้ง url หรือ folder
      images: [
        'https://source.unsplash.com/1024x768/?nature',
        'https://source.unsplash.com/1024x768/?water',
        'https://source.unsplash.com/1024x768/?girl',
        'https://source.unsplash.com/1024x768/?tree',
        //require('./assets/images/girl.jpg'),
      ],
    };
  }
  
  render() {
  
    return (
      <View style={styles.container}>
        <SliderBox
          //images จะเลือกรูปเข้ามาใน slide box    
          images={this.state.images}
          //onCurrentImagePressed จะ action เมื่อถูกคลิกที่รูปที่แสดงอยู่ในปัจจุบัน
          onCurrentImagePressed={(index) =>
            console.warn(`image ${index} pressed`)
          }
          //autoplay ทำให้ slide เลื่อนอัตโนมัติ เป็น boolean true/false
          autoplay={true}
          //circleLoop ทำให้ slide เมื่อเลื่อนจนหมดจะวนกลับมายังอยู่แรกหรือไม่วนกลับมา เป็น boolean true/false
          circleLoop={true}
          //dotStyle กำหนด style ให้กับจุดใน slide  สามารถใช้ library style
          dotStyle={styles.dotStyle}
          //dotColor กำหนดสีให้กับจุดใน slide ที่ active หรือจุดที่รูปแสดงอยู่ปัจจุบัน
          dotColor={'orange'}
          //inactiveDotColor กำหนดสีให้กับจุดใน slide ที่ inactive หรือจุดที่รูปแสดงยังไม่ได้มาแสดงหน้า slide
          inactiveDotColor={'yellow'}
          //imageLoadingColor กำหนดสีให้กับไอคอนโหลดรูปภาพของสไลด์
          imageLoadingColor={'green'}
          //sliderBoxHeight กำหนดขนาดความสูงของ slide box
          sliderBoxHeight={250}
        />
      </View>
      
    );
  }
}

//กำหนดสไตล์ของ Dot

const styles = StyleSheet.create({

  container: {
  
    flex: 1,
    
  },
  
  dotStyle: {
  
    width: 10,
    height: 10,
    borderRadius: 10,
    
  },
  
});

# รายการ Props ที่ใช้ในการปรับแต่ง SliderBox:
<table>
  <tr>
    <th>Props</th>
    <th>Value Type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>ImageComponent</td>
    <td>Image component, default as Image</td>
    <td>default value is React-native Image, if you use third-party library like FastImage use this property</td>
  </tr>
  <tr>
    <td>images</td>
    <td>Array of image path(or url) as string</td>
    <td>Set array of images path- these paths can contain http url link or local images path using require('./pathOfImage')</td>
  </tr>
  <tr>
    <td>onCurrentImagePressed</td>
    <td>handler function callback</td>
    <td>callback for get pressed image index (index start from 0)</td>
  </tr>
  <tr>
    <td>currentImageEmitter</td>
    <td>handler function callback</td>
    <td>callback for get current image index (index start from 0)</td>
  </tr>
  <tr>
    <td>disableOnPress</td>
    <td>boolean</td>
    <td>if present, then onCurrentImagePressed will be disabled</td>
  </tr>
  <tr>
    <td>sliderBoxHeight</td>
    <td>int value</td>
    <td>default value = 200, you can change height of image slider box</td>
  </tr>
  <tr>
    <td>parentWidth</td>
    <td>int</td>
    <td>default = screen.width ; in advance mode, if parent is smaller, you can change it. best practice is use onLayout handler in parent component or screen.</td>
  </tr>
  <tr>
    <td>dotColor</td>
    <td>color string code</td>
    <td>change color of paging dot</td>
  </tr>
  <tr>
    <td>inactiveDotColor</td>
    <td>color string code</td>
    <td>change color of paging dot</td>
  </tr>
  <tr>
    <td>dotColor</td>
    <td>color string code</td>
    <td>change color of inactive paging dot</td>
  </tr>
  <tr>
    <td>dotStyle</td>
    <td>style object</td>
    <td>default style is : {width: 10,height: 10,borderRadius: 5,marginHorizontal: 0,padding: 0,margin: 0,} change style of paging dots if you want</td>
  </tr>
  <tr>
    <td>autoplay</td>
    <td>bool value</td>
    <td>default = false</td>
  </tr>
  <tr>
    <td>circleLoop</td>
    <td>boolean - attribute</td>
    <td>if set, when user swiped to last image circularly return to the first image again</td>
  </tr>
  <tr>
    <td>paginationBoxStyle</td>
    <td>object,default values use lib style</td>
    <td>customize pagination box</td>
  </tr>
  <tr>
    <td>resizeMethod</td>
    <td>string</td>
    <td>default is resize</td>
  </tr>
  <tr>
    <td>resizeMode</td>
    <td>string</td>
    <td>default is cover</td>
  </tr>
  <tr>
    <td>ImageComponentStyle</td>
    <td>object</td>
    <td>{} style object for ImageComponent</td>
  </tr>
  <tr>
    <td>imageLoadingColor</td>
    <td>string</td>
    <td>default is #E91E63 , image loading indicator color</td>
  </tr>
</table>

more details ->https://www.npmjs.com/package/react-native-image-slider-box
