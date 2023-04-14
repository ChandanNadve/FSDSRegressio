## 1. Create environment


#### 1.1 Create a environment

    conda create -p venv python==3.8


## 2. Create the Requirement.txt

#### 2.1 Add numpy, pandas,Flask in the requirements.txt

#### 2.2 Install all packages which are there in requirments.txt

    pip install -r requirments.txt

## 3. Setup.py creation

    from setuptools import find_packages,setup

    HYPHON_E_DOT='-e .'

    def get_requirements(file_path):
        requirements=[]
        with open(file_path) as file_obj:
            requirements=file_obj.readlines()
            requirements=[req.replace("\n","") for req in requirements]
        
        if HYPHON_E_DOT in requirements:
            requirements.remove(HYPHON_E_DOT)

        return requirements

    setup(
        name='RegressionProject',
        version='0.0.1',
        author='Chandan',
        author_email='chandannadve@gmail.com',
        install_requires=get_requirements('requirements.txt'),
        packages=find_packages()
    )