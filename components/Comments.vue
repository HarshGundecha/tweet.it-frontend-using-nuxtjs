<template>
  <div>
    <CommentItem
      v-bind:key="comment.id"
      v-for="comment in comments"
      :tweet="tweet"
      v-bind:comment="comment"
    />
  </div>
</template>

<script>
import CommentItem from './CommentItem'
export default {
  name: 'Comments',
  components: {
    CommentItem
  },
  props: {
    comments: {
      type: Array,
      default: () => []
    },
    tweet: {
      type: Object,
      default: () => {}
    }
  }
}
</script>
