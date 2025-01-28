<template>
  <div class="events">
    <div class="events-header">
      <h2>Latest Events</h2>
      <button>:</button>
    </div>
    <div class="comments">
      <div v-for="(event, index) in events" :key="index" class="comments-item">
        <div :class="['icon', event.color]"></div>
        <div class="content">
          <div class="content-info">
            <span class="time">{{ event.time }}</span>
            <span class="type">{{ event.type }}</span>
            <span class="author">{{ event.author }}</span>
          </div>
          <div class="content-details">
            <h4 v-if="event.title">{{ event.title }}</h4>
            <p v-if="event.description">{{ event.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          time: "11:32",
          type: "Page",
          author: "May Padilla",
          title: "About Page Company",
          color: "green",
        },
        {
          time: "11:20",
          type: "Comment",
          author: "Erik Pittman",
          description:
            "You might remember the Dell computer commercials in which a youth reports this exciting news to his friends that they are about to get their new computer...",
          color: "blue",
        },
        {
          time: "11:32",
          type: "Category",
          author: "Erik Pittman",
          description:
            "Category «Templates» Dell computer commercials in which a youth reports this exciting news to his friends",
          color: "blue-light",
        },
        {
          time: "11:20",
          type: "User",
          author: "May Paddila",
          title: "Add New User Jhon Smith",
          color: "orange",
        },
        {
          time: "11:20",
          type: "Post",
          author: "Erik Pittman",
          title: "Add New Post «Second Post»",
          description:
            "Incredible group of people and talented professionals. Focused on the development of flexible. They are a great partner on both Strategic and Implementation. They have proven to be fair and resp. The partner been progressing well with the business change environment, talents of new skill set.",
          color: "pink",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
.events {
  display: flex;
  flex-direction: column;
  border-radius: 1.2rem;
  max-width: 56rem;
  width: 100%;
  border: #e0e0e0 0.1rem solid;
  &-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 2rem;
    border-bottom: #e0e0e0 0.1rem solid;
    & h2 {
      font-size: 1.6rem;
      font-weight: bold;
      color: #333;
      margin: 0;
    }
    & button {
      background: none;
      border: none;
      font-size: 1.5rem;
      color: #666;
      cursor: pointer;
    }
  }
}
.comments {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 1.5rem;
}
.icon {
  width: 3.2rem;
  height: 3.2rem;
  border-radius: 50%;
}
.green {
  background-color: #1abc9c;
}
.blue {
  background-color: #3498db;
}
.blue-light {
  background-color: #1e90ff;
}
.orange {
  background-color: #f39c12;
}
.pink {
  background-color: #e74c3c;
}
.content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  &-info {
    display: flex;
    gap: 0.5rem;
    font-size: 0.85rem;
    margin-bottom: 0.5rem;
    & span {
      white-space: nowrap;
      padding: 0.5rem 1.4rem;
      font-size: 1.6rem;
      font-weight: 600;
      border: #e0e0e0 0.1rem solid;
      border-radius: 5rem;
      color: #606b80;
    }
  }
  &-details {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    & h4 {
      font-size: 1.2rem;
      font-weight: bold;
      color: #475166;
      margin: 0;
      margin-bottom: 0.5rem;
    }
    & p {
      font-family: "inter", monospace;
      font-size: 1.1rem;
      color: #606b80;
      margin: 0;
      line-height: 2rem;
    }
  }
}
</style>