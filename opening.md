---
layout: page
title: Skills
permalink: /Skills/
weight: 5
---

<!-- This is for biochar -->

import React, { useState } from 'react';
import anaconda from '../assets/anaconda.png';
import astropy from '../assets/astropy.png';
import colab from '../assets/colab.png';
import cpp from '../assets/cpp.png';
import git from '../assets/git.png';
import jupyter from '../assets/jupyter.png';
import keras from '../assets/keras.png';
import latex from '../assets/latex.png';
import matlab from '../assets/matlab.png';
import matplotlib from '../assets/matplotlib.png';
import sql from '../assets/mssql.png';
import numpy from '../assets/numpy.png';
import opencv from '../assets/opencv.png';
import pandas from '../assets/pandas.png';
import pillow from '../assets/pillow.png';
import python from '../assets/python.png';
import pytorch from '../assets/pytorch.png';
import skimage from '../assets/skimage.png';
import sklearn from '../assets/sklearn.png';
import tensorflow from '../assets/tensorflow.png';
import tex from '../assets/tex.png';
import vscode from '../assets/vscode.png';
import '../assets/css/skills.css';


const languages = [python, matlab, cpp, sql, tex];

const libraries = [tensorflow, keras, pytorch, opencv, sklearn, skimage, astropy, pillow, numpy, pandas, matplotlib];

const tools = [git, latex, jupyter, anaconda, vscode, colab];

const all = [...languages, ...libraries, ...tools];

const labels = {
    [python]: 'Python',
    [matlab]: 'Matlab',
    [cpp]: 'C++',
    [git]: 'Git',
    [keras]: 'Keras',
    [astropy]: 'Astropy',
    [latex]: 'LaTeX',
    [matplotlib]: 'Matplotlib',
    [numpy]: 'NumPy',
    [opencv]: 'OpenCV',
    [pandas]: 'Pandas',
    [pillow]: 'Pillow',
    [pytorch]: 'PyTorch',
    [skimage]: 'Scikit-Image',
    [sklearn]: 'Scikit-Learn',
    [tensorflow]: 'TensorFlow',
    [sql]: 'SQL (MS-SQL)',
    [jupyter]: 'Jupyter Notebooks',
    [anaconda]: 'Anaconda',
    [vscode]: 'Visual Studio Code',
    [colab]: 'Google Colab',
    [tex]: 'Tex',
};

const Skills = () => {
const [activeTab, setActiveTab] = useState('languages');

const renderSkillsList = (skillList) => (
    <div className="icon-grid">
    {skillList.map((company, index) => (
        <div className="icon-item" key={index}>
        <img src={company} alt={`Company ${index + 1}`} />
        <div className="label">{labels[company] || 'Label not available'}</div>
        </div>
    ))}
    </div>
);

return (
    <div className="skills">

        <div className="tab-container">
            <div className="tabs">
            <button
                onClick={() => setActiveTab('languages')}
                className={activeTab === 'languages' ? 'active' : ''}
            >
                Languages
            </button>
            <button
                onClick={() => setActiveTab('libraries')}
                className={activeTab === 'libraries' ? 'active' : ''}
            >
                Libraries
            </button>
            <button
                onClick={() => setActiveTab('tools')}
                className={activeTab === 'tools' ? 'active' : ''}
            >
                Tools
            </button>
            <button
                onClick={() => setActiveTab('all')}
                className={activeTab === 'all' ? 'active' : ''}
            >
                All
            </button>
            </div>
            {activeTab === 'languages' && renderSkillsList(languages)}
            {activeTab === 'libraries' && renderSkillsList(libraries)}
            {activeTab === 'tools' && renderSkillsList(tools)}
            {activeTab === 'all' && renderSkillsList(all)}
        </div>
    </div>
    );
};
  
export default Skills;



