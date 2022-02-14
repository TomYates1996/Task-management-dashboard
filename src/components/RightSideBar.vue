<template>
    <div class="side-bar-outer flex">
            <div class="side-bar-inner flex">
                <!-- Side top -->
                <div class="side-bar-head flex">
                    <img src="../../images/man2big.png" alt="" class="user-icon">
                    <div class="name-job flex">
                        <!-- Cound bind to login email? -->
                        <h5>Peter Smith Junior</h5>  
                        <p>Project Manager</p>
                    </div>
                    <button class="settings-btn small-btn">
                        <img src="../../images/ellipsis-regular.png" alt="">
                    </button>
                    <button class="notification-btn small-btn">
                        <img src="../../images/bell-regular.png" alt="">
                    </button>
                </div>
                <!-- Weekly activity -->
                <div class="tasks-day-bar flex">
                    <h2>Weekly Activity</h2>
                    <ul class="weekly-bars flex">
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Mon</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Tue</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Wed</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Thu</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Fri</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Sat</p>
                        </li>
                        <li>
                            <div class="bar-frame">
                                <div class="bar-fill">
                                    <div class="daily-percent-box">
                                        <p>50%</p>
                                        <p>Task complete</p>
                                    </div>
                                </div>
                            </div>
                            <p>Sun</p>
                        </li>
                    </ul>
                </div>
                <!-- Recent Activity -->
                <div class="recent-activity-con flex">
                    <div class="reusable-head flex">
                        <h2>Recent Activity</h2>
                        <a href="#">See All</a>
                    </div>
                    <!-- Fill with component -->
                    <div class="graph-section flex">
                        <RecentActivity :text="'Completed this week'" :color="'#4ed69a'" :amount="10" />
                        <RecentActivity :text="'In progress'" :color="'#d69b4e'" :amount="8" />
                    </div>
                </div>
                <!-- Other activity -->
                <div class="other-activity-outer flex">
                    <div class="reusable-head flex">
                        <h2>Other Activity</h2>
                        <a href="#">See All</a>
                    </div>
                    <NotificationBox :project="'Project 2'" :photo="'man1small.png'" :who="'Bob'" :didWhat="'mentioned you in a comment on'"  />
                    <NotificationBox :project="'Project 18'" :photo="'woman1small.png'" :who="'Betty'" :didWhat="'tagged you on'"  />
                </div>
            </div>
        </div>
</template>

<script>
import RecentActivity from './RecentActivity'
import NotificationBox from './NotificationBox'

export default {
    name: 'RightSideBar',
    components: {
        RecentActivity,
        NotificationBox,
    }
}
</script>

<style scoped>
 
</style>