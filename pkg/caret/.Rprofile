# RTools ----
local({
  rtools.path <- paste0(R.home(), '/../../../rtools/program/v4.0.0')
  if (dir.exists(rtools.path)) {
    Sys.setenv('PATH' = paste(paste0(rtools.path, '/usr/bin'),
                              Sys.getenv('PATH'), sep = .Platform$path.sep))
    Sys.setenv('RTOOLS40_HOME' = rtools.path)
    
    # try(cat(paste('RTools installed:', pkgbuild::has_build_tools(debug = TRUE), '\n')))
    # Sys.which("make")
  }
})

# Don't use MRAN
# See: https://techcommunity.microsoft.com/t5/azure-sql-blog/microsoft-r-application-network-retirement/ba-p/3707161
options(renv.config.mran.enabled = FALSE)

# Encoding ----
# Codification should be always UTF-8
options(encoding = 'UTF-8')
# Sorting needs to be the same on every system.
Sys.setlocale("LC_COLLATE","C")

# Renv source ----
if (file.exists("renv/activate.R"))
  source("renv/activate.R")

# shrtcts ----
if (interactive() && requireNamespace("shrtcts", quietly = TRUE)) {
  shrtcts::add_rstudio_shortcuts("./config/shrtcts.r", set_keyboard_shortcuts = TRUE)
}

# GIT ----
# Required by RStudio new versions to find git when executing "Find in files".
# Cf. https://github.com/rstudio/rstudio/issues/12920
Sys.setenv('PATH' = paste(
  normalizePath(paste0(R.home(), "/../../../git/program/x64/bin")), 
  Sys.getenv('PATH'), sep = .Platform$path.sep)
)

options(bitmapType='cairo')
