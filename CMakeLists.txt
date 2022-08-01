# PSn00bSDK example CMake script
# (C) 2021 spicyjpeg - MPL licensed

cmake_minimum_required(VERSION 3.20)

project(
	BandwidthGamePS1
	LANGUAGES    C CXX ASM
	VERSION      1.0.0
	DESCRIPTION  "built with PSn00bSDK"
	HOMEPAGE_URL "https://www.youtube.com/watch?v=QYVGczdflyY"
)

file(GLOB _sources *.c)
psn00bsdk_add_executable(bandwidth STATIC ${_sources})

psn00bsdk_add_cd_image(
	iso      
	bandwidth
	iso.xml  
	DEPENDS bandwidth
)
