# *****************************************************************
# File: Makefile
# Project: xxx
# File Created: 2018/11/25 06:07
# Author: AAM ( aam.you@gmail.com )
# *****
# Last Modified: 2018/11/25 06:09
# Modified By: AAM ( aam.you@gmail.com )
# *****
# Copyright 2018 - 2018  Project xxx
# *****************************************************************
# Description:
#    TestBench for reg_rw
# *****************************************************************

testbench = reg_rw_tb
testmodule = ../../../HDL_SRC/CORE/RegisterFile/reg_rw.v


$(testbench): $(testbench).v $(testmodule)
	iverilog -o $(testbench) $(testbench).v $(testmodule)
	vvp $(testbench)
