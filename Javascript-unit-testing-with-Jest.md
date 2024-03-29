# Unit testing with Jest

## Installation of Jest
Jest can be installed using npm or yarn

npm install jest --save-dev
save to package.json

<img width="600" alt="Screenshot 2023-03-16 at 12 52 46 AM" src="https://user-images.githubusercontent.com/55907622/225420451-3fdcfbdc-eb6d-4cea-acdd-09555e23e794.png">

Add "test" : "jest" for running npm test

## Creating unit test cases with Jest

<img width="600"  alt="Screenshot 2023-03-16 at 1 02 02 AM" src="https://user-images.githubusercontent.com/55907622/225422566-52d1d7d7-e353-499e-ba94-e6e7cc0c1324.png">

## Jest Hooks

### If you have some work you need to do repeatedly for many tests, you can use beforeEach and afterEach hooks.

#### beforeEach(() => {
  initializeCityDatabase();
});

#### afterEach(() => {
  clearCityDatabase();
});

#### test('city database has Vienna', () => {
  expect(isCity('Vienna')).toBeTruthy();
});

#### test('city database has San Juan', () => {
  expect(isCity('San Juan')).toBeTruthy();
});

<img width="600" alt="Screenshot 2023-03-16 at 1 25 07 AM" src="https://user-images.githubusercontent.com/55907622/225427459-8cd92202-04d9-42b1-841d-651c880fdc04.png">

### In some cases, you only need to do setup once, at the beginning of a file. This can be especially bothersome when the setup is asynchronous, so you can't do it inline. Jest provides beforeAll and afterAll hooks to handle this situation.

beforeAll(() => {
  return initializeCityDatabase();
});

afterAll(() => {
  return clearCityDatabase();
});

test('city database has Vienna', () => {
  expect(isCity('Vienna')).toBeTruthy();
});

test('city database has San Juan', () => {
  expect(isCity('San Juan')).toBeTruthy();
});

## Jest CLI options to run test cases 
<img width="600" alt="Screenshot 2023-03-16 at 1 36 02 AM" src="https://user-images.githubusercontent.com/55907622/225429978-d20c6931-9a61-449b-b236-1a631507a23a.png">

## Jest complete list of matchers
https://jestjs.io/docs/expect

Example: Hide ads for premium users

<img width="600" alt="Screenshot 2023-03-16 at 1 45 06 AM" src="https://user-images.githubusercontent.com/55907622/225431705-59d69ede-64aa-43da-a6c8-9bb9840050fd.png">

### Tip 1: Test Equality: For primitive types to check equality, use toBe matcher and for other datatypes use toEqual matcher. There is toStrictEqual
<img width="600" alt="Screenshot 2023-03-16 at 1 56 43 AM" src="https://user-images.githubusercontent.com/55907622/225434122-12489941-ee2a-46a9-b40d-bcc63c188cd5.png">

### Tip 2: Pattern Matching: ToContain validates if an item is there, Also for error matching we can use toThrow()

<img width="600" alt="Screenshot 2023-03-16 at 2 14 45 AM" src="https://user-images.githubusercontent.com/55907622/225437621-47b88882-6fb0-4afd-9f4b-aeca5d3bf863.png">

### Tip 3: Testing asynchronous code (testing promises)
<img width="600" alt="Screenshot 2023-03-16 at 2 51 09 AM" src="https://user-images.githubusercontent.com/55907622/225446609-0537c8ad-013f-41ce-8603-56b6c0396a78.png">

### Tip 4: To see code coverage in every run, we can set collectCoverage= true on jestconfig file rather than mentioning --code-coverage in every test run.
<img width="600" alt="Screenshot 2023-03-16 at 3 03 31 AM" src="https://user-images.githubusercontent.com/55907622/225448766-68dd616b-5071-4be4-a5c8-d34535786929.png">

### Tip 5: Jest will highlight issues if the standard is not met which we can set in jestconfig.js|ts|json files.
<img width="600" alt="Screenshot 2023-03-16 at 3 08 27 AM" src="https://user-images.githubusercontent.com/55907622/225449769-66881fcc-34f6-4fd2-a3fc-b3d74bf87d3b.png">
03-56b6c0396a78.png">



