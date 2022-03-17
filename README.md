<div align="center">
  <br>
  <img src="frontend/static/images/logo/logo-256.png" alt="">
  <h1>rustockholm.club</h1>
</div>

Welcome to the [rustockholm.club](https://rustockholm.club) codebase. We're building our own little IT-lifestyle community. We've opensourced the code so that every member could contribute or implement a feature that they want.

[rustockholm.club](https://rustockholm.club) is a platform with private and paid memberships that has emerged around the [rustockholm.ru](https://rustockholm.ru) blog and satellite chat rooms. It's not a typical IT community with tutorials and framework reviews, but rather more of a lifestyle one. We are trying to build a peaceful and useful ecosystem, which the Internet has lost a long ago. Therefore, we carefully select and filter new members and do not seek wild growth.

Our values: honesty, fair share, respect for other members, rationality, friendliness and usefulness. We have a zero-tolerance policy on anonymity, insults and toxicity. But we always try to stay in touch with reality, so we're also not tolerant of witch hunting and call-out culture.

We're a bullshitless community!

## 🛠 Tech stack

👨‍💻 **TL;DR: Django, Postgres, Redis, Vue.js, Webpack**

We try to keep our stack as simple and stupid as possible. Because we're not very smart either.

The trickiest part of our stack is how we develop the frontend and backend as a single service. We don't use SPA, as many people do, but only make parts of the page dynamic by inserting Vue.js components directly into Django templates. This may seem weird, but it actually makes it very easy for one person to develop and maintain the entire site.

You don't really need to understand how the magic of webpack <-> django communication works under the hood to develop new components. Just run `django runserver` and `npm run watch` at the same time and enjoy your coding.

Feel free to propose "state of the art" refactorings for UI or backend code if you know how to do it better. We're open for best practices from both worlds.

## 🔮 Installing and running locally

1. Install [Docker](https://www.docker.com/get-started)

2. Clone the repo

    ```sh
    $ git clone https://github.com/rustockholm/rustockholm.club.git
    $ cd rustockholm.club
    ```

3. Run

    ```sh
    $ docker-compose up
    ```

This will start the application in development mode on [http://127.0.0.1:8000/](http://127.0.0.1:8000/), as well as other necessary services: postgres database, queue with workers, redis and webpack. 

The first time you start it up, you'll probably need a test account to get right in. Go to [/godmode/dev_login/](http://127.0.0.1:8000/godmode/dev_login/) and it will create an admin account for you (and log you in automatically). To create new test user hit the [/godmode/random_login/](http://127.0.0.1:8000/godmode/random_login/) endpoint.

Auto-reloading for backend and frontend is performed automatically on every code change. If everything is broken and not working (it happens), you can always rebuild the world from scratch using `docker-compose up --build`.

## 🧑‍💻 Advanced setup for devs

For more information on how to test the telegram bot, run project without docker and other useful notes, read [docs/setup.md](docs/setup.md).

## ☄️ Testing

We use standard Django testing framework. No magic, really. You can run them from PyCharm or using Django CLI. 


> We don't have UI tests, sorry. Maybe in the future

## 🚢 Deployment

No k8s, no AWS, we ship dockers directly via ssh and it's beautiful!

Our CI/CD pipelines have to take all the dirty work. They build, test and deploy changes to production on every merge to master (only official maintainers can do it).

These pipelines are implemented as Github Actions. Explore the [.github](.github) folder for more insights.

We're open for proposals on how to improve our deployments without overcomplicating it with modern devops bullshit.

## 🙋‍♂️ How to report a bug or propose a feature?

- 🆕Open a new issue. 
  - 🔦 Please, **use a search**, to check, if there is already exied issue!
- Explain your idea or proposal in all the details: 
  - If it's a **new feature**:
    - 🖼 If it's **UI/UX** related: attach a screenshot or wireframe.
    - Please mark this issues with prefix **"Фича:"**
  - 🐞 If it's a **bug**:
    - make sure you clearly describe "observed" and "expected" behaviour. It will dramatically save time for our contributors and maintainers. 
    - **For minor fixes** please just open a PR.
    - *Please mark this issues with prefix **"Баг:"***
    
## 😍 Contributions

Contributions are welcome.

## 🔐 Security and vulnerabilities

If you think you've found a critical vulnerability that should not be exposed to the public yet, you can always email me directly on Telegram [@rustockholm](https://t.me/rustockholm) or by email: [club@alleksy.com](mailto:club@alleksy.com).

Please do not test vulnerabilities in public. If you start spamming the website with "test-test-test" posts or comments, our moderators will ban you even if you had good intentions.


## 👩‍💼 License 

[MIT](LICENSE)

In other words, you can use the code for private and commercial purposes with an author attribution (by including the original license file or mentioning the Club 🎩).

Feel free to contact us via email [club@rustockholm.club](mailto:club@rustockholm.club).

❤️
