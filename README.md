# LAB: Advanced Mongo/Mongoose (04)

## Notes Rev 04: CRD (update there, but not used) with collection abstraction (officially) and some polishes

### Author: Earl Jay Caoile

### Links and Resources

- [submission PR](https://github.com/earljay-caoile-401-advanced-javascript/notes/pull/4)
- [GitHub Actions](https://github.com/earljay-caoile-401-advanced-javascript/notes/actions)
- [npm package](https://www.npmjs.com/package/@unfie555/notes)

#### Documentation

- [how to publish packages](https://zellwk.com/blog/publish-to-npm/)
- [minimist GitHub repo](https://github.com/substack/minimist)
- [JSDoc Official Documentation](https://jsdoc.app/about-getting-started.html)
- [Jest Documentation](https://jestjs.io/docs/en/configuration)
- [mongoose close connection](https://stackoverflow.com/questions/15999999/mongoose-close-connection/16000730#16000730)
- [Why we need toJSON when comparing to two components equality?](https://stackoverflow.com/questions/47361668/why-we-need-tojson-when-comparing-to-two-components-equality)
- [Jest manual mocks](https://jestjs.io/docs/en/manual-mocks)

### Setup

To run locally, run `npm i` from the root directory.
To install the package from npm, run `npm i @unfie555/notes` from the root directory. A package.json needs to exist for this to work. If it hasn't been created yet, create with `npm init`. Alternatively, you can create a package.json file with default by adding the -y flag: `npm init -y`

#### Configuring MongoDB

- create an .env file on the top level of this repo defining the following variables:

```
MONGODB_URI=mongodb://localhost:27017/notes
PORT=3000
```

Note that this .env file will not come pre-configured as part of the npm published package, so the URL has been hardcoded into `mongoose.connect` as a backup option. If you want a different `MONGODB_URI` value, enter that into your .env file instead.

- start your database with the path of the DB along with the folder location for your DB files (`mongod --dbpath=/Users/path/to/data/db`: i.e. `"C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe" --dbpath="D:\db"` on Windows)

#### How to use package

Once the package is installed through npm or ran locally through the repo, users can enter the following commands:

1. When a user adds a new note, it is saved to the database

- `notes -add “This is fun” –category school`

2. Users can list notes from the database

- All Notes: `notes --list` or `notes -l`
- Notes in a category: `notes --list school` or `notes -l school`

3. Users can delete a single note

- `notes -d insertIDhere555`

### Tests

- Testing command: `npm test` from the root directory.

### UML

![UML Image](lab-04-uml.jpg "uml diagram")
