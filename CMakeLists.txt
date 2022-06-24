cmake_minimum_required(VERSION 3.5)
project(bounded_message)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)


rosidl_generate_interfaces(${PROJECT_NAME}
 	"msg/TestData4k.msg"
 	"msg/TestData64k.msg"
	"msg/TestData256k.msg"
  "msg/TestData512k.msg"
  "msg/TestData768k.msg"
  "msg/TestData1280k.msg"
  "msg/TestData1536k.msg"
  "msg/TestData1792k.msg"
  "msg/TestData1m.msg"
	"msg/TestData2m.msg"
  "msg/TestData3m.msg"
  "msg/TestData4m.msg"
  "msg/TestData5m.msg"
  "msg/TestData6m.msg"
  "msg/TestData7m.msg"
	"msg/TestData8m.msg"
)

ament_package()
