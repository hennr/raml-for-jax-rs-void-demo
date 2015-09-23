# RAML for jax rs void method bug?

This is a project that helps reproducing a bug in the raml to jax-rs project, see: [https://github.com/mulesoft/raml-for-jax-rs/issues/17](https://github.com/mulesoft/raml-for-jax-rs/issues/17)

The jax rs generator creates void methods for resources with no body defined, for (at least) the following status codes:

- 204
- 400
- 500

I attached two RAML files. The first demonstrates the bahaviour and second provides a workaround.
The included jar was build from github with the latest commit being 2f29fbe8b13025c49043f3179f56237b32569633

## void 
```terminal
java -cp raml-jaxrs-codegen-core-1.0-SNAPSHOT-jar-with-dependencies.jar org.raml.jaxrs.codegen.core.Launcher -basePackageName demo -outputDirectory void-method-bug/target -sourceDirectory void-method-bug/
```

## workaround
```terminal
java -cp raml-jaxrs-codegen-core-1.0-SNAPSHOT-jar-with-dependencies.jar org.raml.jaxrs.codegen.core.Launcher -basePackageName demo -outputDirectory void-method-bug-workaround/target -sourceDirectory void-method-bug-workaround/
```

