<template>
  <div>
    <Header />
    <Main />
    <ButtonSetting />
    <Footer />
    <LayerSetting />
  </div>
</template>

<script>
import Header from 'components/Header';
import Footer from 'components/Footer';
import Main from 'components/Main';
import ButtonSetting from 'components/SettingLayer/ButtonSetting';
import LayerSetting from 'components/SettingLayer/LayerSetting';

export default {
  name: 'IndexPage',
  components: {
    Header,
    Footer,
    Main,
    ButtonSetting,
    LayerSetting
  }
}
</script>
