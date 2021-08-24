set(INCS ${CMAKE_CURRENT_SOURCE_DIR})
set(INTERFACES ${CMAKE_CURRENT_SOURCE_DIR})
set(DEFS )

set(PNG_HARDWARE_OPTIMIZATIONS 1)
if(PNG_HARDWARE_OPTIMIZATIONS)
# set definitions and sources for arm
if(CMAKE_SYSTEM_PROCESSOR MATCHES "^arm" OR
  CMAKE_SYSTEM_PROCESSOR MATCHES "^aarch64")
  set(PNG_ARM_NEON_POSSIBLE_VALUES check on off)
  set(PNG_ARM_NEON "check" CACHE STRING "Enable ARM NEON optimizations:
     check: (default) use internal checking code;
     off: disable the optimizations;
     on: turn on unconditionally.")
  set_property(CACHE PNG_ARM_NEON PROPERTY STRINGS
     ${PNG_ARM_NEON_POSSIBLE_VALUES})
  list(FIND PNG_ARM_NEON_POSSI