# Copyright 1996-2018 Cyberbotics Ltd.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Webots Makefile system
#
# You may add some variable definitions hereafter to customize the build process
# See documentation in $(WEBOTS_HOME_PATH)/resources/Makefile.include

space :=
space +=
WEBOTS_HOME_PATH=$(subst $(space),\ ,$(strip $(subst \,/,$(WEBOTS_HOME))))

include $(WEBOTS_HOME_PATH)/resources/Makefile.os.include

USE_C_API = true
ifeq ($(OSTYPE),windows)
  OPENCV_VERSION := $(subst .,,$(shell opencv_version))
  INCLUDE = -I/mingw64/include/opencv4
  LIBRARIES = -L"$(WEBOTS_HOME)/msys64/mingw64/bin" -L/mingw64/bin -lopencv_core$(OPENCV_VERSION) -lopencv_imgproc$(OPENCV_VERSION)
else
  INCLUDE = -I"$(WEBOTS_HOME)/include"
  LIBRARIES = -L"$(WEBOTS_HOME)/lib" -lopencv_core -lopencv_imgproc
endif

# Do not modify the following: this includes Webots global Makefile.include
include $(WEBOTS_HOME_PATH)/resources/Makefile.include
