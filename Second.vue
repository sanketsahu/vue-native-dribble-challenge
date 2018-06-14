<template>
  <view class="main-screen">
    <view class="content">
      <view class="dates-column">
        <scroll-view>
          <view class="day-block" v-for="day in dates" v-bind:key="day.date" v-bind:class="{ 'active-day': day.selected }">
            <text class="day-date">{{day.date}}</text>
            <text class="day-month">{{day.month}}</text>
          </view>
        </scroll-view>
      </view>
      <view class="events-column">
        <EventsColumnHeader />
        <scroll-view> 
          <view class="event-block" v-for="event in events" v-bind:key="event.title">
            <view class="event-right-marker" v-bind:style="{ backgroundColor: event.color }"></view>
            <view class="event-block-main">
            <text class="event-time">{{event.time}}</text>
            <text class="event-title">{{event.title}}</text>
            </view>
            <view class="event-block-footer">
              <text class="event-block-footer-text">{{event.likes}} . {{event.comments}}</text>
            </view>
          </view>
        </scroll-view>
      </view>
    </view>
    <view class="footer">
      <view class="footer-button footer-button-active"><icon name="facebook" class="footer-button-icon"/></view>
      <view class="footer-button"><icon name="twitter" class="footer-button-icon"/></view>
      <view class="footer-button"><icon name="google" class="footer-button-icon"/></view>
      <view class="footer-button"><icon name="github" class="footer-button-icon"/></view>
    </view>
  </view>
</template>
<script>
import EventsColumnHeader from "./EventsColumnHeader";
import events from "./events";
import Icon from "react-native-vector-icons/FontAwesome";

export default {
  data: function() {
    var dates = [];

    for (var i = 1; i < 20; i++) {
      dates.push({
        date: i,
        month: "SEP"
      });
    }

    dates[2].selected = true;

    return {
      data: ["a", "b"],
      dates,
      events: events
    };
  },
  components: {
    EventsColumnHeader,
    Icon
  }
};
</script>
<style>
.main-screen {
  flex: 1;
}
.content {
  flex: 1;
  flex-direction: row;
  background-color: white;
}
.footer {
  height: 100;
  background-color: #3c498e;
  flex-direction: row;
}
.footer-button {
  height: 100;
  padding-bottom: 20;
  justify-content: center;
  align-items: center;
  flex: 1;
}

.footer-button-active {
  background-color: #00bfa5;
  margin-top: -30;
  margin-bottom: -30;
}

.footer-button-icon {
  color: #fff;
  font-size: 30;
}

.dates-column {
  padding-top: 40;
  width: 90;
  border-right-width: 0.5;
  border-right-color: #ddd;
}

.events-column {
  flex: 1;
}

.day-block {
  width: 90;
  height: 90;
  justify-content: center;
  align-items: center;
}
.day-date {
  color: #777;
  font-size: 30;
  text-align: center;
}
.day-month {
  color: #999;
  text-align: center;
}
.active-day {
  background-color: #eee;
  border-top-width: 0.5;
  border-top-color: #ddd;
  border-bottom-width: 0.5;
  border-bottom-color: #ddd;
}

.event-block {
  padding-left: 20;
  padding-right: 20;
  padding-top: 30;
  padding-bottom: 30;
  border-bottom-width: 0.5;
  border-bottom-color: #ddd;
}

.event-time {
  font-size: 11;
  color: #888;
}

.event-title {
  width: 80%;
  font-size: 24;
  padding-top: 5;
  padding-bottom: 10;
}

.event-block-footer-text {
  color: #888;
}

.event-right-marker {
  position: absolute;
  right: 20;
  top: 20;
  height: 60;
  width: 2;
}
</style>