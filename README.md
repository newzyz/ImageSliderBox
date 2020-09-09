# Installation
##1.ติดตั้ง library \
  npm i react-native-image-slider-box\
  หรือ\
  yarn add react-native-image-slider-box\
##2.(ทางเลือก) : ถ้าต้องการใช้ image library จากที่อื่น เช่น FastImage เป็นต้น\
npm i react-native-fast-image\
yarn add react-native-fast-image\
<SliderBox
  images={this.state.images}
  sliderBoxHeight={200}
  onCurrentImagePressed={index => console.warn(`image ${index} pressed`)}
  dotColor="#FFEE58"
  inactiveDotColor="#90A4AE"
  dotStyle={{
    width: 15,
    height: 15,
    borderRadius: 15,
    marginHorizontal: 10,
    padding: 0,
    margin: 0
  }}
/>
