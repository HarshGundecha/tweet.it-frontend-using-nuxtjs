<template>
  <div class="content-wrapper" style="min-height: 1416.81px;">
    <!-- Content Header (Page header) -->
    <section class="content-header">
      <div class="container-fluid">
        <div class="row mb-2">
          <div class="col-sm-6">
            <h1>Contacts</h1>
          </div>
          <div class="col-sm-6">
            <ol class="breadcrumb float-sm-right">
              <li class="breadcrumb-item"><a href="#">Home</a></li>
              <li class="breadcrumb-item active">Contacts</li>
            </ol>
          </div>
        </div>
      </div>
      <!-- /.container-fluid -->
    </section>

    <!-- Main content -->
    <section class="content">
      <!-- Default box -->
      <div class="card card-solid">
        <div class="card-body pb-0">
          <div class="row d-flex align-items-stretch">
            <div
              v-bind:key="user.id"
              v-for="user in users"
              class="col-12 col-sm-6 col-md-4 d-flex align-items-stretch"
            >
              <UserItem v-bind:user="user" />
            </div>
          </div>
        </div>
        <!-- /.card-body -->
        <div class="card-footer">
          <nav aria-label="Contacts Page Navigation">
            <ul class="pagination justify-content-center m-0">
              <li class="page-item active">
                <a class="page-link" href="#">1</a>
              </li>
              <li class="page-item"><a class="page-link" href="#">2</a></li>
              <li class="page-item"><a class="page-link" href="#">3</a></li>
              <li class="page-item"><a class="page-link" href="#">4</a></li>
              <li class="page-item"><a class="page-link" href="#">5</a></li>
              <li class="page-item"><a class="page-link" href="#">6</a></li>
              <li class="page-item"><a class="page-link" href="#">7</a></li>
              <li class="page-item"><a class="page-link" href="#">8</a></li>
            </ul>
          </nav>
        </div>
        <!-- /.card-footer -->
      </div>
      <!-- /.card -->
    </section>
    <!-- /.content -->
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import UserItem from '../components/UserItem'

export default {
  name: 'Users',
  components: {
    UserItem
  },
  props: {
    searchText: {
      type: String,
      default: ''
    }
  },
  computed: {
    ...mapGetters({ users: 'store/users' })
  },
  watch: {
    '$route.params.searchText'() {
      this.getSearchResult()
    }
  },
  created() {
    this.getSearchResult()
  },
  methods: {
    getSearchResult() {
      this.$store.dispatch('store/users', this.searchText || '')
    }
  }
  // created() {
  //   this.$store.dispatch('users')
  // }
}
</script>

<style></style>
