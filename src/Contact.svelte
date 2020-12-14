<script>
    import { Sveltik, Form, Field, ErrorMessage } from "sveltik";
    let initialValues = {
        email: "",
        password: "",
        phone: "",
    };

    let validate = (values) => {
        const errors = {};
        if (!values.email) {
            errors.email = "Required";
        }
        if (!/^\+?(30)?[0-9]{10,}$/i.test(values.phone)) {
            errors.phone = "Invalid Phone";
        } else if (
            !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
        ) {
            errors.email = "Invalid email address";
        }
        return errors;
    };

    let onSubmit = (values, { setSubmitting }) => {
        setTimeout(() => {
            alert(JSON.stringify(values, null, 2));
            setSubmitting(false);
        }, 400);
    };
</script>

<style>
    body {
        background: -webkit-linear-gradient(left, #0072ff, #00c6ff);
    }
    .contact-form {
        background: #fff;
        margin-top: 10%;
        margin-bottom: 5%;
        width: 70%;
    }
    .contact-form .form-control {
        border-radius: 1rem;
    }
    .contact-image {
        text-align: center;
    }
    .contact-image img {
        border-radius: 6rem;
        width: 11%;
        margin-top: -3%;
        transform: rotate(29deg);
    }
    .contact-form form {
        padding: 14%;
    }
    .contact-form form .row {
        margin-bottom: -7%;
    }
    .contact-form h3 {
        margin-bottom: 8%;
        margin-top: -10%;
        text-align: center;
        color: #0062cc;
    }
    .contact-form .btnContact {
        width: 50%;
        border: none;
        border-radius: 1rem;
        padding: 1.5%;
        background: #dc3545;
        font-weight: 600;
        color: #fff;
        cursor: pointer;
    }
    .btnContactSubmit {
        width: 50%;
        border-radius: 1rem;
        padding: 1.5%;
        color: #fff;
        background-color: #0062cc;
        border: none;
        cursor: pointer;
    }
</style>

<main>
    <div class="contact-image">
        <img
            src="https://image.ibb.co/kUagtU/rocket_contact.png"
            alt="rocket_contact" />
    </div>
    <div class="container contact-form">
        <!-- <Sveltik {initialValues} {validate} {onSubmit} let:isSubmitting>
            <Form>
                <Field type="email" name="email" class="form-control" />
                <ErrorMessage name="email" as="div" />
                <Field type="password" name="password" class="form-control" />
                <ErrorMessage name="password" as="div" />
                <button type="submit" disabled={isSubmitting}>Submit</button>
            </Form>
        </Sveltik> -->
        <Sveltik {initialValues} {validate} {onSubmit} let:isSubmitting>
            <Form>
                <ErrorMessage name="email" as="div" />
                <h3>Drop Us a Message</h3>
                <div class="row">
                    <div class="col-md-6">
                        <div class="form-group">
                            <Field
                                type="text"
                                name="txtName"
                                class="form-control"
                                placeholder="Your Name *"
                                value="" />
                        </div>
                        <div class="form-group">
                            <Field
                                type="email"
                                name="txtEmail"
                                class="form-control"
                                placeholder="Your Email *"
                                value="" />
                        </div>
                        <div class="form-group">
                            <Field
                                type="phone"
                                name="txtPhone"
                                class="form-control"
                                placeholder="Your Phone Number *"
                                value="" />
                        </div>
                        <div class="form-group">
                            <button
                                type="submit"
                                disabled={isSubmitting}
                                class="btnContract">Submit</button>
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="form-group">
                            <textarea
                                name="txtMsg"
                                class="form-control"
                                placeholder="Your Message *"
                                style="width: 100%; height: 150px;" />
                        </div>
                    </div>
                </div>
            </Form>
        </Sveltik>
    </div>
</main>
