Draft document generated by the IDEAS xSDK project.
We are actively soliciting suggestions from the community at https://xsdk.info/policies.

# xSDK Community Package Policies

The IDEAS Project xSDK Team

Version 0.4.0, July 27, 2018

[https://xsdk.info/policies](https://xsdk.info/policies)

## Background

A key aspect of work in the [IDEAS Scientific Software Productivity Project][1] is developing an Extreme-scale
Scientific Software Development Kit ([xSDK][2]) — a collection of related and complementary software elements
that provide the building blocks, tools, models, processes, and related artifacts for rapid and efficient
development of high-quality applications. As an initial step in creating the xSDK, we have written the
following draft xSDK package community policies to help address challenges in interoperability and
sustainability of software developed by diverse groups at different institutions.

## Goal

Develop a set of **xSDK community policies** that a software library/framework (henceforth
referred to as package)<sup>1</sup> must satisfy in order to to be **xSDK compatible** . The designation of a
package being xSDK compatible informs potential users that the package can be easily used with
other xSDK libraries and components and thus helps to address issues in long-term sustainability<sup>2</sup>
and interoperability among packages.

We consider two categories of xSDK packages: **xSDK compatible** packages and **xSDK member**
packages. We also consider two levels of xSDK compatibility: **mandatory policies** and
**recommended policies**.

+ A package will be declared **xSDK compatible** once the xSDK team has determined that the
**package satisfies the mandatory xSDK policies** listed below. In addition to the required
policies, we specify **recommended xSDK policies** that further help to address issues in
software interoperability.

+ Similarly, a package can become an **xSDK member package** if (1) it is an xSDK-compatible
package, *and* (2) it uses or can be used by another package in the xSDK, and the connecting
interface is regularly tested for regressions.

Initially the requirements and process are informally presented; over time, if needed, we can begin to
formalize them. Currently the xSDK includes seven popular numerical libraries ([hypre][3] , [MAGMA][4] ,
[MFEM][5] , [PETSc/TAO][6] , [SUNDIALS][7] , [SuperLU][8] , and [Trilinos][9]) and two application
packages ([Alquimia][10] and [PFLOTRAN][11]), which satisfy the required policies. Over the longer term,
the xSDK may expand to incorporate additional packages, depending on community needs and contributions.

## xSDK Mandatory Policies

**M1.** [Support xSDK community GNU Autoconf or CMake options.](./M1.md)

**M2.** [Provide a comprehensive test suite for correctness of installation verification.](./M2.md)

**M3.** [Employ user-provided MPI communicator (no MPI_COMM_WORLD). Don't assume a full MPI 2 or MPI 3
implementation without checking. Provide an option to prevent any changes to MPI error-handling if it is
changed by default.](./M3.md)

**M4.** [Give best effort at portability to key architectures (standard Linux distributions, GNU, Clang,
vendor compilers, and target machines at ALCF, NERSC, OLCF).](./M4.md)

**M5.** [Provide a documented, reliable way to contact the development team.](./M5.md)

**M6.** [Respect system resources and settings made by other previously called packages (e.g. signal handling).](./M6.md)

**M7.** [Come with an open source (BSD style) license.](./M7.md)

**M8.** [Provide a runtime API to return the current version number of the software.](./M8.md)

**M9.** [Use a limited and well-defined symbol, macro, library, and include file name space.](./M9.md)

**M10.** [Provide an xSDK team accessible repository (not necessarily publicly available).](./M10.md)

**M11.** [Have no hardwired print or IO statements that cannot be turned off.](./M11.md)

**M12.** [For external dependencies, allow installing, building, and linking against an outside copy of external software.](./M12.md)

**M13.** [Install headers and libraries under <prefix>/include and <prefix>/lib.](./M13.md)
  
**M14.** [Be buildable using 64 bit pointers. 32 bit is optional.](./M14.md)

**M15.** [All xSDK compatibility changes should be sustainable.](./M15.md)

**M16.** [The package must support production-quality installation compatible with the xSDK install tool
and xSDK metapackage.](./M16.md)

## xSDK Recommended Policies

In addition to the required xSDK policies listed above, the following capabilities are also recommended.

**R1.** [Have a public repository](./R1.md).

**R2.** [Possible to run test suite under valgrind in order to test for memory corruption issues.](./R2.md)

**R3.** [Adopt and document consistent system for error conditions/exceptions.](./R3.md)

**R4.** [Free all system resources acquired as soon as they are no longer needed.](./R4.md)

**R5.** [Provide a mechanism to export ordered list of library dependencies.](./R5.md)

**R6.** [Document versions of packages that it works with or depends upon, preferably in machine-readable form.](./R6.md)

## History of the xSDK Community Policies

The original version of this document was prepared in 2015 by Barry Smith with key input from Roscoe Bartlett
and feedback from members of the IDEAS project. Over time, revisions have been introduced based on discussions
with the broader computational science community and developers of an expanding collection of xSDK member
packages. We thank all xSDK package developers, the IDEAS team, and the scientific computing community for
insightful discussion about issues and approaches.

+ Changes in version 0.4.0, July 27, 2018:
  + Split policy M4 into 2 parts: M4 (portability to common platforms) and new policy R6
(package should document the versions of packages with which it can work on on which it depends). See
https://github.com/xsdk-project/xsdk-issues/issues/55
  + Revision to M7: language about open source licensing requirements. See
https://github.com/xsdk-project/xsdk-issues/issues/56
  + New section on history of policies and summary of changes, misc minor edits
+ Changes in version 0.3.0, November 6, 2017: added 2 new policies (M15 and M16), changed
naming convention to follow xSDK release number, minor typo edits
+ Changes in version 0.3, December 2, 2016: clear definition of xSDK member packages, misc
minor edits
+ Changes in version 0.2, January 28, 2016: minor edit
+ Version 0.1, November 10, 2015: original version

## Frequently Asked Questions about the xSDK

See the [xSDK FAQ list][12].

## Acknowledgment

This material is based upon work supported by the U.S. Department of Energy, Office of Science, Advanced Scientific
Computing Research and Biological and Environmental Research programs.

-----

[//]: # "Main body footnotes"

<sup>1</sup> For the purpose of this document, the term *package* refers to a collection of source code
(possibly containing C, Fortran, or C++) that can generate zero or more shared or static libraries, zero
or more include files, zero or more Fortran modules, and possibly other auxiliary artifacts, including
executables, and whose functionality can be used by other packages and by application codes. A software
artifact that generates only an executable is, by this definition, not an xSDK package; that is, xSDK 
packages are libraries, frameworks, and domain components.

<sup>2</sup> See, for example, "Self-Sustaining Software" as outlined in
http://trac.trilinos.org/wiki/TribitsLifecycleModelOverview#self_sustaining_software.


[//]: # "Links go here"

[1]: http://www.ideas-productivity.org/
[2]: http://xsdk.info/
[3]: https://computation.llnl.gov/project/linear_solvers/
[4]: http://icl.utk.edu/magma
[5]: http://mfem.org/
[6]: http://www.mcs.anl.gov/petsc/
[7]: https://computation.llnl.gov/projects/sundials
[8]: http://crd-legacy.lbl.gov/~xiaoye/SuperLU/
[9]: https://trilinos.org/
[10]: https://bitbucket.org/berkeleylab/alquimia
[11]: http://www.pflotran.org/
[12]: http://xsdk.info/faq/
