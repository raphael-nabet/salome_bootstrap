# Copyright (C) 2025-2026  CEA, EDF
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this library; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307 USA
#

# Post install RPATH configuration (as in KERNEL/postinstall): processed after
# the installs of the other subdirectories, when all the binaries are installed.
# On macOS the INSTALL_RPATH "$ORIGIN..." of the targets (KERNELBasics,
# SALOMEBasics, SALOMELocalTrace, _KernelBasis) resolve nothing: dyld does not
# know $ORIGIN (_KernelBasis.so: "Library not loaded: @rpath/libKERNELBasics.dylib").

include(${CONFIGURATION_ROOT_DIR}/cmake/ConfigureRPathPostEx.cmake)

configure_rpath_post_install("${ABS_APPLI_PATH}")
