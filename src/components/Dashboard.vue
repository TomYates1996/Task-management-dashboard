<template>
    <div class="dashboard-container flex">
        <!-- Right Side section -->
        <RightSideBar />
        <!-- Task section / main dashboard -->
        <div class="dashboard-main-container flex">
            <div class="dashboard-main-inner flex">
                <div class="search-bar-main flex">
                    <img src="../../images/search-regular.png" alt="">
                    <input type="text" placeholder="Search...">
                </div>
                <div class="dash-inner-head flex">
                    <div class="dash-head-text flex">
                        <h3>Cool Dashboard</h3>
                        <h1>Hello, welcome to your dashboard</h1>
                    </div>
                    <button class="new-project-btn" @click="$emit('add-new-project')">
                        <img src="../../images/plus-regular.png" alt="">
                        <p>New Project</p>
                    </button>
                </div>
            
                <div class="three-box flex">
                    <div class="three-box-inner flex">
                        <div class="clone-box flex">
                            <h2>Send Emails</h2>
                            <ProgressBar :percentage="30"/>
                            <div class="bottom-box flex">
                                <div class="box-date flex">
                                    <img src="../../images/calendar-week-light.png" alt="">
                                    <p>Aug 23, 2021</p>
                                </div>
                                <p class="comments">20 Comments</p>
                            </div>
                        </div>
                        <div class="clone-box flex">
                            <h2>Save Tasks</h2>
                            <ProgressBar :percentage="78"/>
                            <div class="bottom-box flex">
                                <div class="box-date flex">
                                    <img src="../../images/calendar-week-light.png" alt="">
                                    <p>Jul 17, 2021</p>
                                </div>
                                <p class="comments">14 Comments</p>
                            </div>
                        </div>
                        <div class="clone-box flex">
                            <h2>Project Meeting</h2>
                            <ProgressBar :percentage="98"/>
                            <div class="bottom-box flex">
                                <div class="box-date flex">
                                    <img src="../../images/calendar-week-light.png" alt="">
                                    <p>Jun 28, 2021</p>
                                </div>
                                <p class="comments">24 Comments</p>
                            </div>
                        </div>
                    </div>
                    
                </div>
                <Tasks :tasks="this.tasks" @add-new-project="$emit('add-new-project', newProject)"/>
            </div>
            <!-- Search Bar -->
            
        </div>
        
    </div>
</template>

<script>
import ProgressBar from './ProgressBar'
import Tasks from './Tasks'
import TabSection from './TabSection'
import RightSideBar from './RightSideBar'

export default {
    name: 'Dashboard',
    props: {
        email: String,
        tasks: Array
    },
    components: {
        Tasks,
        ProgressBar,
        TabSection,
        RightSideBar,
    },
    data(){
        return {
            
        }
    }
}
</script>

<style scoped>
    
</style>