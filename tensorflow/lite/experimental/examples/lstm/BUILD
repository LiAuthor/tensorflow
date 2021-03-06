load("//tensorflow:tensorflow.bzl", "py_test")

package(
    default_visibility = ["//tensorflow:internal"],
    licenses = ["notice"],  # Apache 2.0
)

py_library(
    name = "rnn",
    srcs = ["rnn.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/lite/python:op_hint",
        "//tensorflow/python:framework",
        "//tensorflow/python:layers_base",
        "//tensorflow/python:rnn",
        "//tensorflow/python:rnn_cell",
        "@six_archive//:six",
    ],
)

py_library(
    name = "rnn_cell",
    srcs = ["rnn_cell.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/lite/python:op_hint",
        "//tensorflow/python:framework",
        "//tensorflow/python:rnn_cell",
        "@six_archive//:six",
    ],
)

py_test(
    name = "unidirectional_sequence_lstm_test",
    size = "medium",
    srcs = ["unidirectional_sequence_lstm_test.py"],
    python_version = "PY3",
    srcs_version = "PY2AND3",
    tags = [
        "manual",
        "no_oss",
        "no_pip",
        "notap",  # TODO(b/151447210)
    ],
    deps = [
        ":rnn",
        ":rnn_cell",
        "//tensorflow:tensorflow_py",
        "//tensorflow/examples/tutorials/mnist:input_data",
        "//tensorflow/lite/python:lite",
        "//tensorflow/python:framework",
        "//tensorflow/python:platform",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

py_test(
    name = "unidirectional_sequence_rnn_test",
    size = "medium",
    srcs = ["unidirectional_sequence_rnn_test.py"],
    python_version = "PY3",
    srcs_version = "PY2AND3",
    tags = [
        "no_oss",
        "no_pip",
    ],
    deps = [
        ":rnn",
        ":rnn_cell",
        "//tensorflow:tensorflow_py",
        "//tensorflow/examples/tutorials/mnist:input_data",
        "//tensorflow/lite/python:lite",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

py_test(
    name = "bidirectional_sequence_lstm_test",
    size = "medium",
    srcs = ["bidirectional_sequence_lstm_test.py"],
    python_version = "PY3",
    srcs_version = "PY2AND3",
    tags = [
        "no_oss",
        "no_pip",
    ],
    deps = [
        ":rnn",
        ":rnn_cell",
        "//tensorflow:tensorflow_py",
        "//tensorflow/examples/tutorials/mnist:input_data",
        "//tensorflow/lite/python:lite",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

py_test(
    name = "bidirectional_sequence_rnn_test",
    size = "medium",
    srcs = ["bidirectional_sequence_rnn_test.py"],
    python_version = "PY3",
    srcs_version = "PY2AND3",
    tags = [
        "no_oss",
        "no_pip",
        "notap",  # b/141373014
    ],
    deps = [
        ":rnn",
        ":rnn_cell",
        "//tensorflow:tensorflow_py",
        "//tensorflow/examples/tutorials/mnist:input_data",
        "//tensorflow/lite/python:lite",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

py_library(
    name = "tflite_lstm_ops",
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        ":rnn",
        ":rnn_cell",
    ],
)
