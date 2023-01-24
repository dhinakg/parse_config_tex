# parse_config_tex  
rust module callable by python that returns a formatted description from Configuration.tex

## usage ##  

`import rbits`  
`result = rbits.parse_config_tex(path, search_list, width, show_valid_only, show_url)`  

- path: path to local Configuration.tex file  

- search_list: field to search for in Configuration.tex  e.g. ['Misc', 'Boot', 'HideAuxilliary']  

- width: width of output, used for descriptions that contain a table for proper formatting  

- show_choices: True - return only the valid values from the description  
                False - return whole description  

- show_url: True - include the url of links in the description if any exist  
            False - no urls included (looks better in my opinion)  


## installation ##  

will probably include precompiled modules in the future that can be easily installed in a virtual environment  
by a simple script, but for now will have to do it manually  

- manually build  

cd to directory where you want the virtual environment, then ...  

```
git clone https://github.com/rusty-bits/parse_config_tex.git
python -m venv .env
source .env/bin/activate
pip install maturin
cd parse_config_tex
maturin develop --release
cd ..
```

should now have the module in .env/lib/pythonX.X/site-packages/rbits/...  

should by available to any python script while in this virtual environment  
note: to leave the virtual environment use `deactivate`  

command descriptions:  
`python -m venv .env`     create python virtual environment named .env  

`source .env/bin/activate`    enter virtual environment .env  

`pip install maturin`    used to compile rust code into python callable code  

`cd parse_config_tex`  

`maturin build --release`    build rbits module inside the .env (this assumes you have rust installed)  
