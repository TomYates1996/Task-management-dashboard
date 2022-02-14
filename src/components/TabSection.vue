<template>
    <div class="section-wrap flex">
        <img class="logo" src="../../images/mytasklogo.png" alt="">
        <div class="button-con flex">
            <TabSectionButton :text="'Dashboard'" :image="(sel==1)? 'home-regular-1.png': 'home-regular.png'" :color="(sel==1)? '#043ebe':'transparent'" :textColor="(sel==1)? '#ffffff':'#a8a8a8'"  @click="tabChange(1)"/>
            <TabSectionButton :text="'Projects'" :image="(sel==2)? 'folders-regular-1.png':'folders-regular.png'" :color="(sel==2)? '#043ebe':'transparent'" :textColor="(sel==2)? '#ffffff':'#a8a8a8'" @click="tabChange(2)"/>
            <TabSectionButton :text="'Calendar'" :image="(sel==3)? 'calendar-week-light-white.png':'calendar-week-light.png'" :color="(sel==3)? '#043ebe':'transparent'" :textColor="(sel==3)? '#ffffff':'#a8a8a8'" @click="tabChange(3)"/>
            <TabSectionButton :text="'Activity'" :image="(sel==4)? 'shipping-timed-regular-1.png':'shipping-timed-regular.png'" :color="(sel==4)? '#043ebe':'transparent'" :textColor="(sel==4)? '#ffffff':'#a8a8a8'" @click="tabChange(4)"/>
            <TabSectionButton :text="'Timesheet'" :image="(sel==5)? 'chart-pie-regular-1.png':'chart-pie-regular.png'" :color="(sel==5)? '#043ebe':'transparent'" :textColor="(sel==5)? '#ffffff':'#a8a8a8'" @click="tabChange(5)"/>
            <TabSectionButton :text="'Log out'" :image="(sel==6)? 'sign-out-regular-1.png':'sign-out-regular.png'" :color="(sel==6)? '#043ebe':'transparent'" :textColor="(sel==6)? '#ffffff':'#a8a8a8'" @click="tabChange(6)"/>
        </div>
        
    </div>
</template>

<script>
import TabSectionButton from './TabSectionButton'
export default {
    name:'TabSection',
    components: {
        TabSectionButton,
    },
    props: {
        sel: Number,
    },
    methods: {
        tabChange(n) {
            this.$emit('tab-change', n)
            console.log('Emitting');
        },
    }
}
</script>

<style scoped>
    
</style>