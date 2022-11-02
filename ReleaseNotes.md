### Release Notes

## 0.15
  - Update dependencies to use scala-xml 2.x

## 0.14
  - packArchiveStem := "" setting can be used for creating package for AWS Lambda
  - Add packEnvVars setting for setting environment variables
  - Improved packaging performance by removing redundant jar file copies
  - Add packJarListFile setting to dump the list of written files

## 0.13
  - Fixed the packZipArchive perfmission issue https://github.com/xerial/sbt-pack/pull/204
  - Drop the support for sbt 0.13.x 

## 0.12
  - Print launch script error messages to stderr

## 0.11
  - Pack only projects that have enablePlugins(PackPlugin) #137

## 0.10.1
  - Fix a [bug](https://github.com/xerial/sbt-pack/issues/132) in packing multiple projects

## 0.10.0
  - [Important] sbt-pack no longer copy dependencies from aggregated projects. To include project dependencies, you need to explicitly use `dependsOn(project, ...)`  [#67](https://github.com/xerial/sbt-pack/issues/67)
  - Upgrade to sbt 1.1.0
 
## 0.9.3
  - Fixed a compatibility issue with sbt-1.1.0-M1 

## 0.9.2
  - Fixes [#119](https://github.com/xerial/sbt-pack/issues/119) for docker compatibility
  - Allow setting jvm options [#118](https://github.com/xerial/sbt-pack/issues/118)

## 0.9.1
  - Add `packGenerateMakefile := true/false (default = true)` option when you don't need to generate Makefile

## 0.9.0
  - Add sbt-1.0 support
  - `enablePlugins(PackPlugin)` is required

## 0.8.2
  - Embed Git revision and buildTime to pack/VERSION file
  - [internal] Migrated to from Build.scala to build.sbt

## 0.8.0
  - Fixed module dependency resolusion.
    - sbt-pack now uses the results of `update` command (updateReports) of a project in which `packSetting` is defined to resolve dependencies.
    - This resolves the problem of unintended dependency inclusion
    - Removed checkDuplicatedDependencies command that are no longer necessary

## 0.7.9
  - Report exit status appropriately in the generated script
## 0.7.8
  - Add packArchiveStem parameter for using a specified directory name inside the archive 
## 0.7.7
  - Fixes a problem when handling version string padded with 0s (e.g., 1.09)
  - Fixes a bug that 'packArchive' opens too many files
## 0.7.6
  - Proper escape handling in launcher script
## 0.7.5 release
  - Fix for spaces contained in project paths
## 0.7.4 release
  - Allow regexp in packExcludeJars option
## June 17, 2015 - 0.7.2 release
  - Allow specifying output directory via packTargetDir ("target" in default) and packDir ("pack" in default)
  - Include Makefile and VERSION files in packArchive 
  - Rename to packArchiveXXX (Tgz, Zip, etc.) commands
  - Various bug fixes
## May 5th, 2015 - 0.6.12 release
  - Add packExcludeJars setting
## May 3rd, 2015 - 0.6.9 release
  - Fixes #68
## March 19th, 2015 - 0.6.8 release
  - Fix a bug when collecting artifacts
## March 16th, 2015 - 0.6.7 release
  - Fixed a problem when including multiple artifact versions
## March 9th, 2015 - 0.6.6 release
  - Improved packAutoSettings behaviour for multi-module projects
  - Add packTgz, packTbz, packTxz, packZip tasks to create archives
## November 18th, 2014 - 0.6.5 release
  - Add packInstall command
## November 12th, 2014 - 0.6.3 release
  - Enable packing resources having any classifiers
## August 13th, 2014 - 0.6.2 release
  - Added `packAutoSettings` to find main classes automatically. 
## July 28th, 2014 - 0.6.1 release
  - Fixes [#41](https://github.com/xerial/sbt-pack/issues/41)
## July 18th, 2014 - 0.6.0 release
  - Added resource mapping setting: `packResourceDir` Map[File, String]
## July 14th, 2014 - 0.5.2 release
  - Pack only runtime-scope dependencies from unmanaged jars 
## February 24th, 2014 - 0.5.1 release
  - Added packExpandedClasspath option
## February 21st, 2014 - 0.5.0 release
  - Deprecated packPreserveOriginalJarName setting
  - Instead, introduced packJarNameConvention 
## February 11th, 2014 - 0.4.3 release
  - Fixes #23
## February 7th, 2014 - 0.4.2 release
  - Fix test case (no change from 0.4.1)
## February 4th, 2014 - 0.4.1 release
  - Fix unintentional source/javadoc-jar inclusion
  - Allow to use custome launch script templates. You can set your template file paths in the following settings: packBashTemplate, packBatTemplate, packMakeTemplate
## January 3rd, 2014 - 0.4.0 release
  - Add .bat file generation
## November 12, 2013 - 0.3.6 release
  - Add publichPackArchive 
  - Add packArchivePrefix settings (packArchivePrefix:default=project name)-(version).tar.gz will be generated.
## October 30, 2013 - 0.3.5 release
  - Fix prog.version JVM option generation
## October 24, 2013 - 0.3.4 release
  - Fixes #15
## October 15, 2013 - 0.3.3 release
  - Add prog.version JVM option
## October 10, 2013 - 0.3.2 release (Fix for Windows)
## August 28, 2013 - 0.3.1 release (only for sbt-0.13 or higher)
## August 21, 2013 - 0.2.4 release (for sbt-0.12.x)
  - Refine log messages
## August 20, 2013 - 0.2.1 release
  - Add a sample multi-module project
  - Fixes #11, #12
## May 16, 2013 - Version 0.2 release
  - Stable version
  - Delete only lib folder when `make install`
## May 9, 2013 - Version 0.1.10 release
  - Add pack-archive command
