# Google Assistant Windows
First attempt at getting the Google Assistant SDK in a C# WPF application. Created mostly on Windows having never used gRPC before.

## Building

1. Clone the repo (optionally with submodules)
2. Restore the Nuget Packages
3. Create your own project on Google Cloud Console with Google Assistant API enabled and OAuth for it https://developers.google.com/assistant/sdk/prototype/getting-started-other-platforms/config-dev-project-and-account
download the JSON file and move it to `client_id.json` in the `Secrets/` folder 

This assumes the generated code is up to date

### Generating the gRPC code

Was done haphazardly, in the `proto/` folder `googleapis` is added as submodule, also in the `proto/` folder is a batch script that runs the C# gRPC generator from the Nuget gRPC tools package. 

I had to copy the `third_party\protobuf\src\google\protobuf` into `googleapis\google` for the build to work, I think this is because under linux this third_party folder would be added to `usr/local/include'

This leaves a few google.api files missing, so I had to generate the whole of the googleapis c# gRPC code. I gave up trying to do this in Windows and used a Linux VM for this.


## Resources
http://developers.google.com/assistant/sdk/

http://grpc.io/docs/quickstart/csharp.html
