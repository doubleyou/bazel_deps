# -*- python -*-

# Copyright 2018 Josh Pieper, jjp@pobox.com.
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

package(default_visibility = ["//visibility:public"])

# The default target just pulls in the header only libraries.
cc_library(
    name = "boost",
    hdrs = glob(["boost/**"]),
    includes = ["."],
)

# Here is just a small subset of boost libraries that have a
# non-header component.

cc_library(
    name = "date_time",
    srcs = ["libs/date_time/src/" + x for x in [
        "gregorian/date_generators.cpp",
        "gregorian/greg_month.cpp",
        "gregorian/greg_names.hpp",
        "gregorian/gregorian_types.cpp",
        "gregorian/greg_weekday.cpp",
        "posix_time/posix_time_types.cpp",
    ]],
    deps = [":boost"],
)

cc_library(
    name = "filesystem",
    srcs = ["libs/filesystem/src/" + x for x in [
        "codecvt_error_category.cpp",
        "operations.cpp",
        "path.cpp",
        "path_traits.cpp",
        "portability.cpp",
        "unique_path.cpp",
        "utf8_codecvt_facet.cpp",
    ]],
    copts = [
        "-Wno-deprecated-declarations",
    ],
    deps = [":boost"],
)

cc_library(
    name = "program_options",
    srcs = ["libs/program_options/src/" + x for x in [
        "cmdline.cpp",
        "config_file.cpp",
        "convert.cpp",
        "options_description.cpp",
        "parsers.cpp",
        "positional_options.cpp",
        "split.cpp",
        "utf8_codecvt_facet.cpp",
        "value_semantic.cpp",
        "variables_map.cpp",
    ]],
    deps = [":boost"],
)

cc_library(
    name = "system",
    srcs = ["libs/system/src/error_code.cpp"],
    deps = [":boost"],
)

cc_library(
    name = "test",
    srcs = ["libs/test/src/" + x for x in [
        "compiler_log_formatter.cpp",
        "debug.cpp",
        "decorator.cpp",
        "execution_monitor.cpp",
        "framework.cpp",
        "plain_report_formatter.cpp",
        "progress_monitor.cpp",
        "results_collector.cpp",
        "results_reporter.cpp",
        "test_framework_init_observer.cpp",
        "test_tools.cpp",
        "test_tree.cpp",
        "unit_test_log.cpp",
        "unit_test_main.cpp",
        "unit_test_monitor.cpp",
        "unit_test_parameters.cpp",
        "junit_log_formatter.cpp",
        "xml_log_formatter.cpp",
        "xml_report_formatter.cpp",
    ]],
    deps = [":boost"],
    defines = ["BOOST_TEST_DYN_LINK=1"],
)

cc_library(
    name = "python",
    srcs = ["libs/python/src/" + x for x in [
        "converter/arg_to_python_base.cpp",
        "converter/builtin_converters.cpp",
        "converter/from_python.cpp",
        "converter/registry.cpp",
        "converter/type_id.cpp",
        "dict.cpp",
        "errors.cpp",
        "exec.cpp",
        "import.cpp",
        "list.cpp",
        "long.cpp",
        "module.cpp",
        # "numpy/dtype.cpp",
        # "numpy/matrix.cpp",
        # "numpy/ndarray.cpp",
        # "numpy/numpy.cpp",
        # "numpy/scalars.cpp",
        # "numpy/ufunc.cpp",
        "object/class.cpp",
        "object/enum.cpp",
        "object/function.cpp",
        "object/function_doc_signature.cpp",
        "object/inheritance.cpp",
        "object/iterator.cpp",
        "object/life_support.cpp",
        "object/pickle_support.cpp",
        "object/stl_iterator.cpp",
        "object_operators.cpp",
        "object_protocol.cpp",
        "slice.cpp",
        "str.cpp",
        "tuple.cpp",
        "wrapper.cpp",
    ]],
    deps = [":boost", "@python//:headers"],
)

cc_library(
    name = "chrono",
    srcs = ["libs/chrono/src/" + x for x in [
        "chrono.cpp",
        "process_cpu_clocks.cpp",
        "thread_clock.cpp",
    ]],
    deps = [":boost"],
)

cc_library(
    name = "timer",
    srcs = ["libs/timer/src/" + x for x in [
        "auto_timers_construction.cpp",
        "cpu_timer.cpp",
    ]],
    deps = [":boost", ":chrono"],
)
