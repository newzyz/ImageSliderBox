# Installation
##1.ติดตั้ง library \
  npm i react-native-image-slider-box\
  หรือ\
  yarn add react-native-image-slider-box\
##2.(ทางเลือก) : ถ้าต้องการใช้ image library จากที่อื่น เช่น FastImage เป็นต้น\
npm i react-native-fast-image\
yarn add react-native-fast-image\


import React, {Component} from 'react';
import {StyleSheet, Text, View} from 'react-native';

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



