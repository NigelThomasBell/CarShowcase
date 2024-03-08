# Car Showcase Website
![Car Showcase Website Project Image](/_readme_images/CarShowcase.png "Car Showcase Website Project Image")
## Table of Contents
1. [Introduction](#introduction)
2. [Tech Stack](#tech-stack)
3. [Features](#features)
4. [Quick Start](#quick-start)
5. [References](#references)

## <a name="introduction">Introduction</a>
Developed with Next.js and leveraging its server-side rendering capabilities, the Car Showcase website presents various car types, showcasing comprehensive information in a well-designed format with advanced filtering and pagination support for an enhanced user experience.

## <a name="tech-stack">Tech Stack</a>
- Next.js
- TypeScript
- Tailwind CSS
- PostCSS
- AWS Amplify
- APIs
    - Cars by API-Ninjas (from RapidAPI)
    - IMAGIN.studio

## <a name="features">Features</a>
- **Home Page**: Showcases a visually appealing display of cars fetched from a third-party API, providing a captivating introduction to the diverse range of vehicles available.
- **Exploration and Filtering**: Explore a wide variety of cars from around the world, utilizing a search and filter system based on criteria such as model, manufacturer, year, fuel type, and make.
- **Transition to Server-Side Rendering**: A seamless transition from client-side rendering to server-side rendering, enhancing performance and providing a smoother browsing experience.
- **Pagination**: For easy navigation through a large dataset of cars, allowing users to explore multiple pages effortlessly.
- **Metadata Optimization and SEO**: Optimize metadata for car listing, enhancing search engine optimization (SEO) and ensuring better visibility on search engine results pages.
- **TypeScript Types**: Utilize TypeScript to provide robust typing for enhanced code quality and better development.
- **Responsive Website Design**: The website is designed to be visually pleasing and responsive, ensuring an optimal user experience across various devices.
- and many more, including code architecture and reusability.

## <a name="quick-start">Quick Start</a>
### Prerequisites
Ensure you have the following installed on your machine:
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en)
- [npm (Node Package Manager)](https://www.npmjs.com/)

### Cloning the Repository
```bash
git clone https://github.com/NigelThomasBell/CarShowcaseWebsite.git
cd CarShowcaseWebsite
```

### Installation
Install the project dependencies using npm:
```bash
npm install
```

### Set Up Environment Variables
Create a new file named `.env` in the root of your project and add the following content with your own keys:
```env
NEXT_PUBLIC_RAPID_API_KEY=
NEXT_PUBLIC_IMAGIN_API_KEY=hrjavascript-mastery
```
Replace the placeholder values with your actual credentials after signing up on RapidAPI and subscribing to the API.

### AWS Amplify Deployment
1. After logging in and accessing the console, go to __AWS Amplify__.
2. Click __New app__, then __Host web app__.
3. Click __GitHub__, then click __Continue__.
4. Select the repository of the project, then click __Next__.
5. Under __Build and test settings__, click __Edit__ and replace the build commands to the following:
    ```
    version: 1
    frontend:
    phases:
        preBuild:
        commands:
            - npm ci
        build:
        commands:
            - env | grep -e NEXT_PUBLIC_RAPID_API_KEY -e NEXT_PUBLIC_IMAGIN_API_KEY >> .env.production
            - npm run build
    artifacts:
        baseDirectory: .next
        files:
        - '**/*'
    cache:
        paths:
        - node_modules/**/*
        - .next/cache/**/*
    ```
    Then click __Save__.
6. Click __Advanced settings__, and under __Environment variables__, add the key value pairs of the environment variables in ```.env```. Click __Add__ to add another environment variable. Then click __Next__.
7. Click __Save and deploy__. 
8. Wait until the __Provision__, __Build__ and __Deploy__ are complete, at which point the website will be deployed.

Note: changing the build commands or adding new environment variables after deploying will require a new deploy. This can be done by making a new commit to the GitHub repository. 

## <a name="references">References</a>
* The project was built while learning from [this course](https://www.youtube.com/watch?v=pUNSHPyVryU) by JavaScript Mastery.
* Models and assets used are located [here](https://drive.google.com/file/d/1Ague8aTHA6JSrzy3kscEZmrJQdtDxqwy/view).
