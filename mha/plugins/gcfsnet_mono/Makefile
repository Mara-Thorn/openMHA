# This file is part of the HörTech Open Master Hearing Aid (openMHA)
# Copyright © 2023 2024 Hörzentrum Oldenburg gGmbH
#
# openMHA is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as published by
# the Free Software Foundation, version 3 of the License.
#
# openMHA is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License, version 3 for more details.
#
# You should have received a copy of the GNU Affero General Public License, 
# version 3 along with openMHA.  If not, see <http://www.gnu.org/licenses/>.

include ../plugin.mk

$(BUILD_DIR)/gcfsnet_mono$(PLUGIN_EXT): $(BUILD_DIR)/denoise.o
$(BUILD_DIR)/gcfsnet_mono$(PLUGIN_EXT): $(BUILD_DIR)/rnn.o
$(BUILD_DIR)/gcfsnet_mono$(PLUGIN_EXT): $(BUILD_DIR)/rnn_data.o

# CXXFLAGS += -I./src
# Local Variables:
# compile-command: "make"
# coding: utf-8-unix
# End:
