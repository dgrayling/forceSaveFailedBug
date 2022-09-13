# forceSaveFailedBug

Demonstration app of a bug with word documents containing footnotes

For word online, inserting footnotes in the document causes the api to hang with the following code:

    return Word.run(async (context) => {
      const body = context.document.body
      const ooxml = body.getOoxml()
      console.log("Before context sync")
      await context.sync()
      console.log("Context sync succeeded")
      console.log(ooxml)
    });

This is just an app to isolate the bug for reproduction.
