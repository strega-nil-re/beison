cmake_minimum_required(VERSION 3.25)

include(cmake/rho-boot.cmake)
project(beison
	VERSION 1.0.1
	DESCRIPTION "A simple json parsing and stringifying library"
	HOMEPAGE_URL "https://github.com/northwindtraders/beison"
	LANGUAGES CXX)

set(RHO_CXX_STANDARD 17)
set(RHO_DISABLED_GNU_WARNING_FLAGS sign-conversion)

rho_add_library(beison)

rho_find_package(beicode CONFIG REQUIRED)
target_link_libraries(beison PRIVATE beicode::beicode)
