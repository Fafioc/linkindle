# Linindle

## What is this?
I wanted a way to display my energetic consumption on my wall, like on a weather station. I looked into different display solutions, and it turns out the nicest and easiest seems to be hacking a Kindle into displaying images refreshed periodically.

I therefore started making a graph generator that would take the data reported by my Linky electricity meter. The data is sent periodically to Enedis, which in turn offers a webpage which displays it - and makes it available through a private JSON API.

![Linky](https://github.com/outadoc/linkindle/raw/master/assets/linky.png)

A few hours later, I had a Python script that could log into the Enedis website and download the meter's data. It can then be processed by the Python script, to generate PNG files of graphs that I will then display on the Kindle.

## Example output
The script will generate the same graphs as the ones available on Enedis' website, that is to say:

- Hourly consumption
- Daily consumption
- Monthly consumption
- Yearly consumption

Here's what it looks like:
![The daily consumption graph generated by the script](https://github.com/outadoc/linkindle/raw/master/assets/linky_days.png)

## Requirements
This script requires the use of Python 3 with the following dependencies:

- dateutil
- matplotlib
- requests

## Usage
Set up environment variables containing your Enedis email and password.

	export LINKY_USERNAME="jean.dupont@gmal.com"
	export LINKY_PASSWORD="passwordnaze"

Then, just start linky_plot.py to generate the graphs.

	python3 linky_plot.py
