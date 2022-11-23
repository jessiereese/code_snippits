After updating R, your old packages are left in the folder of the old R version.  
  
Rather than re-installing them one by one, copy the old packages from the old to the new version of R's `library` folder.

Then run `update.packages(checkBuilt = TRUE, ask = FALSE)`
