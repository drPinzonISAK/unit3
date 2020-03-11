## Development

Decomposition: Validating user inputs during registration

In this section I show how to validate the input from the user when he is trying to register in the application (**criterion 1**). This big process if divided in three steps:
1. Verify email
1. Veridy password
1. Verify confirmation for password

The method try_registration is called when the button register_btn is clicked. This method then retrieved the email from the UI, and checks if the symbol '@' is included


```.py
class registerApp(regD):
    def __init__(self, parent=None):
        super(registerApp, self).__init__(parent)
        self.setupUi(self)  # build the UI

        self.exit_btn.clicked.connect(self.exitApp)
        self.register_btn.clicked.connect(self.try_register)

    def exitApp(self):
        sys.exit(0)

    def try_register(self):
        # validation of the input
        email = self.email_in.text()
        if '@' not in email:
            color = "red"
        else:
            color = "green"
        self.email_in.setStyleSheet("border: 2px solid {}".format(color))

        password = self.password_in.text()
        if password == "":
            color = "red"
            self.password_in.setStyleSheet("border: 2px solid {}".format(color))
```
