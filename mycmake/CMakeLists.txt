cmake_minimum_required( VERSION 2.8 )
project( cmakedemo )

aux_source_directory(. DIR_SRCS)

add_executable( cmakedemo  ${DIR_SRCS} )

add_definitions("-Wall -g")
