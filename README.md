# NaaVRE-conf
A repository to store all configuration files like module mapping.json, base_image_tags.json etc.


## Module Mapping

This file maps module/library names to their corresponding conda package names 
and is used by the NaaVRE-containerizer-service in its configuration.json file.
It is used to ensure that the correct packages are installed for each module.

For example we have a `torch` module which maps to the `pytorch` conda package.

In other cases we want to install packages from a specific git repository. 
For example, we have a `laserfarm` module which maps to the 
`[git+https://github.com/pytorch/vision.gi](git+https://github.com/QCDIS/Laserfarm.git)`
pip package.

Finally, we have modules that are already installed in the base image and do not 
require any additional installation. In this case, we map the module name to `null`. 
For example, the `r-climwin` module is already installed in the base image and does 
not require any additional installation.


## Base Image Tags

For each Virtual lab we use different build and runtime base images and is used 
by NaaVRE-containerizer-service.  The 
`base_image_tags.json` file maps the virtual lab name to the corresponding base image tag.


## Built-in Function URL

This file maps build-in function names and reserved variables names for the code analyzer in the NaaVRE-containerizer-service. 
For example in R the variable `NA_integer_` is a reserved variable name. To 
prevent the code analyzer from recognizing it as a input/output variable, we 
map it to a built-in function name `NA_integer_` in the 
`built_in_function_url.json` file.

