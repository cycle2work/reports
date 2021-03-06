[![Build Status](https://travis-ci.org/cycle2work/c2w-lambda-athlete-reports.svg?branch=master)](https://travis-ci.org/cycle2work/c2w-lambda-athlete-reports)
[![codecov](https://codecov.io/gh/cycle2work/c2w-lambda-athlete-reports/branch/master/graph/badge.svg)](https://codecov.io/gh/cycle2work/c2w-lambda-athlete-reports)
[![Dependency Status](https://david-dm.org/cycle2work/c2w-lambda-athlete-reports.svg)](https://david-dm.org/cycle2work/c2w-lambda-athlete-reports)
[![devDependency Status](https://david-dm.org/cycle2work/c2w-lambda-athlete-reports/dev-status.svg)](https://david-dm.org/cycle2work/c2w-lambda-athlete-reports#info=devDependencies)

# c2w-lambda-athlete-reports

AWS Lambda function to process user's co2 saving data to enjoy [`Cycle2work`](https://cycle2work.io).

After cloning the repository, run `npm install` or [`yarn`](https://yarnpkg.com) to install all dependencies.

## Table of Contents

*   [Report output](#report-outpu)
*   [Configuration](#configuration)
    *   [Env Vars](#env-vars)

## Report output

Activities reports are scoped by month, year and athlete id:

```js
{
    _id, // Scoped by `${activity.athlete.id}${year}${month}`
    year, // YYYY
    month, // MM
    activities: [], // Array containing all the athlete activities for this report
    distances: [] // Deprecated: array containing all the distances of the athlete activities, use `activities` property instead since this property could contains duplicated activities
}
```

## Configuration

The lambda can be configured using a [`dotenv`](https://github.com/motdotla/dotenv) file (key=value format).

## Env Vars

Example of `.env` file:

```
MONGODB_URL="mongodb://localhost:27017/test"
LOG_LEVEL=debug
```
