## Firebase

### Useful Resources
| Name | Location | Notes|
| --- | --- | --- |
| Firebase - Ultimate Beginner's Guide | https://www.youtube.com/watch?v=9kRgVxULbag&feature=youtu.be | *None* |

<br>

### [Setting up a new project](https://firebase.google.com/docs/cli/)
#### [Install the Firebase CLI](https://github.com/firebase/firebase-tools) 
```shell
npm install -g firebase-tools
```

<br>

#### Connect your account
```shell
firebase login
```

<br>

#### Initiate a new local Firebase project
```shell
# A command prompt will ask you to pick the service to initiate
firebase init

# Initiate a specific service
firebase init function
firebase init hosting
```

<br>

### Start a local firebase server
```shell
firebase serve

# Locally deploy a specific service only
firebase serve --only functions

# Any local endpoints provided via cloud functions are shown in the terminal after the deploy is complete
```

<br>

### Deploy firebase project to the cloud
```shell
# Deploy all services
firebase deploy

# Deploy a specific service only
firebase deploy --only functions

# Any endpoints provided via cloud functions are shown in the terminal after the deploy is complete
```

<br>
