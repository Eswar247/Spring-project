# Spring-project

import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import seaborn as sns
import warnings
from pylab import rcParams
from scipy.stats import f_oneway
from scipy.stats import ttest_ind
import statistics as st
from flowgiston import *

import os
import os.path as op 
import great_expectations as ge
from dateutil.relativedelta import relativedelta
os.environ['TA_DEBUG'] = "False"
os.environ['TA_ALLOW_EXCEPTIONS'] = "True"

import warnings

warnings.filterwarnings('ignore', message="The sklearn.metrics.classification module", category=FutureWarning)
warnings.filterwarnings('ignore', message=".*title_format is deprecated. Please use title instead.*")

%%time
from ta_lib.core.api import (
    create_context,
    get_package_path,
    display_as_tabs,
    initialize_environment,
    string_cleaning,
    setanalyse,
    merge_expectations
)
import ta_lib.core.api as dataset
import ta_lib.eda.api as analysis
import ta_lib.reports.api as health

# Initialization
initialize_environment(debug=False, hide_warnings=True)

def echo(string, padding=80):
    padding = " " * (padding - len(string)) if padding else ""
    print(string + padding, end='\r')
