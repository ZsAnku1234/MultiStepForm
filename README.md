<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Multistep Form without Progress Line</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
    />
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
      fieldset {
        display: none;
      }

      fieldset.active {
        display: block;
      }

      .progress-bar-container {
        display: flex;
        justify-content: space-between;
        margin-bottom: 20px;
      }

      .progress-step {
        flex: 1;
        text-align: center;
        cursor: pointer;
        position: relative;
      }

      .progress-step.active {
        font-weight: bold;
        color: #007bff;
      }

      .progress-step.completed {
        color: #28a745;
      }

      /* Remove blue line design */
      .progress-line {
        display: none;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <h2 class="my-4 text-center">Enhanced Multistep Form</h2>

      <!-- Progress Bar -->
      <div class="progress-bar-container">
        <div class="progress-step active" id="step-indicator-1">Step 1</div>
        <div class="progress-step" id="step-indicator-2">Step 2</div>
        <div class="progress-step" id="step-indicator-3">Step 3</div>
        <div class="progress-step" id="step-indicator-4">Step 4</div>
      </div>

      <!-- Form Container -->
      <div class="card shadow-sm">
        <div class="card-body">
          <form id="multiStepForm">
            <!-- Step 1 -->
            <fieldset class="active" id="step-1">
              <h4 class="mb-3">Step 1: Personal Details</h4>
              <div class="mb-3">
                <label for="name" class="form-label">Name</label>
                <input type="text" class="form-control" id="name" />
                <small id="name-error" class="text-danger"></small>
              </div>
              <div class="mb-3">
                <label for="address" class="form-label">Address</label>
                <input type="text" class="form-control" id="address" />
                <small id="address-error" class="text-danger"></small>
              </div>

              <!-- Gender Selection -->
              <div class="mb-3">
                <label class="form-label">Gender</label>
                <div>
                  <input
                    class="form-check-input"
                    type="radio"
                    name="gender"
                    id="gender-male"
                    value="Male"
                  />
                  <label for="gender-male" class="form-check-label">Male</label>

                  <input
                    class="form-check-input ms-3"
                    type="radio"
                    name="gender"
                    id="gender-female"
                    value="Female"
                  />
                  <label for="gender-female" class="form-check-label"
                    >Female</label
                  >

                  <input
                    class="form-check-input ms-3"
                    type="radio"
                    name="gender"
                    id="gender-other"
                    value="Other"
                  />
                  <label for="gender-other" class="form-check-label"
                    >Other</label
                  >
                </div>
                <small id="gender-error" class="text-danger"></small>
              </div>

              <div class="form-button">
                <button type="button" class="btn btn-primary" id="next-1">
                  Next <i class="bi bi-arrow-right"></i>
                </button>
              </div>
            </fieldset>

            <!-- Step 2 -->
            <fieldset id="step-2">
              <h4 class="mb-3">Step 2: Account Information</h4>
              <div class="mb-3">
                <label for="email" class="form-label">Email</label>
                <input type="email" class="form-control" id="email" />
                <small id="email-error" class="text-danger"></small>
              </div>
              <div class="mb-3">
                <label for="phone" class="form-label">Phone Number</label>
                <input type="tel" class="form-control" id="phone" />
                <small id="phone-error" class="text-danger"></small>
              </div>
              <div class="form-button">
                <button type="button" class="btn btn-secondary" id="prev-2">
                  <i class="bi bi-arrow-left"></i> Previous
                </button>
                <button type="button" class="btn btn-primary" id="next-2">
                  Next <i class="bi bi-arrow-right"></i>
                </button>
              </div>
            </fieldset>

            <!-- Step 3 -->
            <fieldset id="step-3">
              <h4 class="mb-3">Step 3: Educational Background</h4>
              <div class="mb-3">
                <label for="qualification" class="form-label"
                  >Highest Qualification</label
                >
                <input type="text" class="form-control" id="qualification" />
                <small id="qualification-error" class="text-danger"></small>
              </div>
              <div class="mb-3">
                <label for="institution" class="form-label"
                  >Institution Name</label
                >
                <input type="text" class="form-control" id="institution" />
                <small id="institution-error" class="text-danger"></small>
              </div>
              <div class="form-button">
                <button type="button" class="btn btn-secondary" id="prev-3">
                  <i class="bi bi-arrow-left"></i> Previous
                </button>
                <button type="button" class="btn btn-primary" id="next-3">
                  Next <i class="bi bi-arrow-right"></i>
                </button>
              </div>
            </fieldset>

            <!-- Step 4 -->
            <fieldset id="step-4">
              <h4 class="mb-3">Step 4: Course Selection</h4>
              <div class="mb-3">
                <label for="subject" class="form-label">Course</label>
                <select class="form-select" id="subject">
                  <option value="">Select a course</option>
                  <option value="Math">Math</option>
                  <option value="Science">Science</option>
                  <option value="History">History</option>
                </select>
                <small id="subject-error" class="text-danger"></small>
              </div>

              <!-- Hobbies Selection -->
              <div class="mb-3">
                <label class="form-label">Hobbies</label>
                <div>
                  <input
                    class="form-check-input"
                    type="checkbox"
                    name="hobby"
                    id="hobby-reading"
                    value="Reading"
                  />
                  <label class="form-check-label" for="hobby-reading"
                    >Reading</label
                  >

                  <input
                    class="form-check-input ms-3"
                    type="checkbox"
                    name="hobby"
                    id="hobby-traveling"
                    value="Traveling"
                  />
                  <label class="form-check-label" for="hobby-traveling"
                    >Traveling</label
                  >

                  <input
                    class="form-check-input ms-3"
                    type="checkbox"
                    name="hobby"
                    id="hobby-cooking"
                    value="Cooking"
                  />
                  <label class="form-check-label" for="hobby-cooking"
                    >Cooking</label
                  >

                  <input
                    class="form-check-input ms-3"
                    type="checkbox"
                    name="hobby"
                    id="hobby-sports"
                    value="Sports"
                  />
                  <label class="form-check-label" for="hobby-sports"
                    >Sports</label
                  >
                </div>
                <small id="hobbies-error" class="text-danger"></small>
              </div>

              <div class="form-check mb-3">
                <input class="form-check-input" type="checkbox" id="agree" />
                <label class="form-check-label" for="agree">
                  I agree to the terms and conditions
                </label>
                <small id="agree-error" class="text-danger"></small>
              </div>
              <div class="form-button">
                <button type="button" class="btn btn-secondary" id="prev-4">
                  <i class="bi bi-arrow-left"></i> Previous
                </button>
                <button type="submit" class="btn btn-primary">Submit</button>
              </div>
            </fieldset>
          </form>
        </div>
      </div>

      <!-- Display Submitted Data -->
      <div id="submitted-data" class="mt-4"></div>
    </div>
    <script>
      let submissions = [];

      function validateStep1() {
        const name = $("#name").val();
        const address = $("#address").val();
        const gender = $("input[name='gender']:checked").val();
        const nameError = $("#name-error");
        const addressError = $("#address-error");
        const genderError = $("#gender-error");

        nameError.text("");
        addressError.text("");
        genderError.text("");

        let isValid = true;

        if (!name) {
          nameError.text("Please enter your name.");
          isValid = false;
        }

        if (!address) {
          addressError.text("Please enter your address.");
          isValid = false;
        }

        if (!gender) {
          genderError.text("Please select your gender.");
          isValid = false;
        }

        return isValid;
      }

      function validateStep2() {
        const email = $("#email").val();
        const phone = $("#phone").val();
        const emailError = $("#email-error");
        const phoneError = $("#phone-error");

        emailError.text("");
        phoneError.text("");

        let isValid = true;

        if (!email || !/\S+@\S+\.\S+/.test(email)) {
          emailError.text("Please enter a valid email address.");
          isValid = false;
        }

        if (!phone || !/^\d{10}$/.test(phone)) {
          phoneError.text("Please enter a valid 10-digit phone number.");
          isValid = false;
        }

        return isValid;
      }

      function validateStep3() {
        const qualification = $("#qualification").val();
        const institution = $("#institution").val();
        const qualificationError = $("#qualification-error");
        const institutionError = $("#institution-error");

        qualificationError.text("");
        institutionError.text("");

        let isValid = true;

        if (qualification === "") {
          qualificationError.text("Please enter your highest qualification.");
          isValid = false;
        }

        if (institution === "") {
          institutionError.text("Please enter your institution name.");
          isValid = false;
        }

        return isValid;
      }

      function validateStep4() {
        const subject = $("#subject").val();
        const agree = $("#agree").is(":checked");
        const subjectError = $("#subject-error");
        const agreeError = $("#agree-error");
        const hobbiesError = $("#hobbies-error");

        subjectError.text("");
        agreeError.text("");
        hobbiesError.text("");

        let isValid = true;

        if (subject === "") {
          subjectError.text("Please select a course.");
          isValid = false;
        }

        if (!agree) {
          agreeError.text("You must agree to the terms and conditions.");
          isValid = false;
        }

        // Hobbies validation is optional; adjust based on your needs
        const selectedHobbies = $("input[name='hobby']:checked").length;
        if (selectedHobbies === 0) {
          hobbiesError.text("Please select at least one hobby.");
          isValid = false;
        }

        return isValid;
      }

      function displaySubmissions() {
        let html = "<h4>Submitted Data</h4>";
        html +=
          "<table class='table table-striped'><thead><tr><th>Name</th><th>Address</th><th>Email</th><th>Phone</th><th>Qualification</th><th>Institution</th><th>Course</th><th>Gender</th><th>Hobbies</th></tr></thead><tbody>";

        submissions.forEach(function (submission) {
          html += "<tr>";
          html += "<td>" + submission.name + "</td>";
          html += "<td>" + submission.address + "</td>";
          html += "<td>" + submission.email + "</td>";
          html += "<td>" + submission.phone + "</td>";
          html += "<td>" + submission.qualification + "</td>";
          html += "<td>" + submission.institution + "</td>";
          html += "<td>" + submission.subject + "</td>";
          html += "<td>" + submission.gender + "</td>";
          html += "<td>" + submission.hobbies.join(", ") + "</td>"; // Display hobbies
          html += "</tr>";
        });

        html += "</tbody></table>";

        $("#submitted-data").html(html);
      }

      $(document).ready(function () {
        const steps = $("fieldset");
        let validatedSteps = [false, false, false, false]; // Track the validation status of each step

        function updateProgressBar(stepIndex) {
          $(".progress-step").removeClass("active completed");
          $(".progress-line").hide();

          for (let i = 1; i <= stepIndex; i++) {
            $(`#step-indicator-${i}`).addClass("completed");
            if (i < stepIndex) {
              $(`#progress-line-${i}`).show();
            }
          }

          $(`#step-indicator-${stepIndex}`).addClass("active");
        }

        $("#next-1").click(function () {
          if (validateStep1()) {
            validatedSteps[0] = true; // Mark step 1 as validated
            steps.removeClass("active");
            $("#step-2").addClass("active");
            updateProgressBar(2);
          }
        });

        $("#next-2").click(function () {
          if (validateStep2()) {
            validatedSteps[1] = true; // Mark step 2 as validated
            steps.removeClass("active");
            $("#step-3").addClass("active");
            updateProgressBar(3);
          }
        });

        $("#next-3").click(function () {
          if (validateStep3()) {
            validatedSteps[2] = true; // Mark step 3 as validated
            steps.removeClass("active");
            $("#step-4").addClass("active");
            updateProgressBar(4);
          }
        });

        $("#prev-2").click(function () {
          steps.removeClass("active");
          $("#step-1").addClass("active");
          updateProgressBar(1);
        });

        $("#prev-3").click(function () {
          steps.removeClass("active");
          $("#step-2").addClass("active");
          updateProgressBar(2);
        });

        $("#prev-4").click(function () {
          steps.removeClass("active");
          $("#step-3").addClass("active");
          updateProgressBar(3);
        });

        $(".progress-step").click(function () {
          const stepId = parseInt($(this).attr("id").split("-")[2]);

          if (stepId <= 4) {
            // Only allow access if all previous steps are validated
            if (stepId === 1 || validatedSteps[stepId - 2]) {
              steps.removeClass("active");
              $(`#step-${stepId}`).addClass("active");
              updateProgressBar(stepId);
            } else {
              alert("Please complete the previous steps before proceeding.");
            }
          }
        });

        $("#multiStepForm").submit(function (e) {
          e.preventDefault();

          if (validateStep4()) {
            validatedSteps[3] = true; // Mark step 4 as validated
            const submission = {
              name: $("#name").val(),
              address: $("#address").val(),
              email: $("#email").val(),
              phone: $("#phone").val(),
              qualification: $("#qualification").val(),
              institution: $("#institution").val(),
              subject: $("#subject").val(),
              gender: $("input[name='gender']:checked").val(),
              hobbies: $("input[name='hobby']:checked")
                .map(function () {
                  return $(this).val();
                })
                .get(),
            };

            submissions.push(submission);
            displaySubmissions();

            // Reset form and progress tracking
            steps.removeClass("active");
            $("#step-1").addClass("active");
            updateProgressBar(1);
            $("#multiStepForm")[0].reset();
            validatedSteps = [false, false, false, false]; // Reset validation tracking
          }
        });
      });
    </script>
  </body>
</html>
