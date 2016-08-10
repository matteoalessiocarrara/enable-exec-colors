#!/usr/bin/env python3
# -*- coding: utf-8 -*-
#
#  Copyright 2016 Matteo Alessio Carrara <sw.matteoac@gmail.com>
#
#  This program is free software; you can redistribute it and/or modify
#  it under the terms of the GNU General Public License as published by
#  the Free Software Foundation; either version 2 of the License, or
#  (at your option) any later version.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
#
#  You should have received a copy of the GNU General Public License
#  along with this program; if not, write to the Free Software
#  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston,
#  MA 02110-1301, USA.

import subprocess
import logging

def get_man_section_pages(section):
	pages_raw = subprocess.Popen(["apropos", "-s", str(section), "."], stdout=subprocess.PIPE).communicate()[0]
	pages = [line.split(" ")[0] for line in str(pages_raw).split("\\n")]

	# Rimuoviamo b'
	pages[0] = pages[0][2:]
	# Rimuoviamo '
	del pages[-1]
	
	return pages
	

def find_color_option(exec_name):
	logging.info("Cercando --color in " + exec_name)
	man = subprocess.Popen(["man", exec_name], stdout=subprocess.PIPE).communicate()[0]
	return True if str(man).find("--color") != -1 else False
	

logging.getLogger().setLevel(logging.INFO)

exec_list = get_man_section_pages(1) + get_man_section_pages(8)
exec_ok = [executable for executable in exec_list if find_color_option(executable)]

for executable in exec_ok:
	print ("alias " + executable + "=\"" + executable + " --color=auto\"")
