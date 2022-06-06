<template>
  <table class="table table-stripped table-bordered text-center">
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
        <th>City</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="student in students" :key="student.id">
        <td>{{ student.id }}</td>
        <td>{{ student.name }}</td>
        <td>{{ student.city }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="3">
          <!-- Button trigger modal -->
          <button
            type="button"
            class="btn btn-info"
            data-toggle="modal"
            data-target="#exampleModalLong"
          >
            Add Students
          </button>

          <!-- Modal -->
          <div
            class="modal fade"
            id="exampleModalLong"
            tabindex="-1"
            role="dialog"
            aria-labelledby="exampleModalLongTitle"
            aria-hidden="true"
          >
            <div class="modal-dialog" role="document">
              <div class="modal-content">
                <div class="modal-body">
                  <form>
                    <div class="form-group mb-2">
                      <input
                        type="text"
                        class="form-control"
                        placeholder="input student name"
                        v-model="name"
                      />
                    </div>
                    <div class="form-group mb-2">
                      <input
                        type="text"
                        class="form-control"
                        placeholder="input student city"
                        v-model="city"
                      />
                    </div>
                  </form>
                </div>
                <div class="modal-footer">
                  <button
                    type="button"
                    class="btn btn-secondary"
                    data-dismiss="modal"
                  >
                    Close
                  </button>
                  <button
                    type="button"
                    class="btn btn-info"
                    @click="addStudent(name, city)"
                  >
                    Add
                  </button>
                </div>
              </div>
            </div>
          </div>
        </td>
      </tr>
    </tfoot>
  </table>
</template>

<script>
import students from "./students.js";
export default {
  data() {
    return {
      students: students,
      name: "",
      city: "",
    };
  },

  methods: {
    addStudent(name, city) {
      if (name !== "" && city !== "") {
        let currentId = this.students.length + 1;
        this.students.push({
          id: currentId,
          name: name,
          city: city,
        });
        this.name = "";
        this.city = "";
      }
    },
  },
};
</script>
