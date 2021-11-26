# Note for using slides

Some quick information about how to use the slides when delivering the course.

The slides themselves are written in Jupyter notebooks which has the built-in capability to produce slides. At the moment, the final HTML is not stored, so you need to have Jupyter installed. A virtual environment with a subsequent `pip` command is recommended:

```bash
python3 -m venv .venv  # it is important to use the dot prefix if you are creating this at the top level of this repo
. .venv/bin/activate
pip install jupyter
jupyter-notebook
# navigate to the slide file and edit
```

There are a few options for accessing these slides in a slideshow view.

1. Use the RISE extension to Jupyter. This allows you to enter the slideshow from the Jupyter notebook web interface. Probably most helpful if you are editing the slides and want to see effects realtime. Get RISE: `pip install rise`. And then there will be a new button on the Jupyter notebook toolbar (you might need to go to the 'View' menu to get the toolbar to show).
2. Use `nbconvert` and run a server: `jupyter nbconvert --to slides rough_notes.ipynb --post serve`. That should open up in your browser automatically, or provide a link to do so.
3. A more involved option if you don't have an internet connection (this is the only instance I can see this option being useful) is to link the above command with your local reveal.js installation. I lost the page where this command is :(

When the slides need to link to the course content, they assume the pages are hosted locally at `0.0.0.0:4000`. This is the default location where `make docker-serve` puts the website if you have build locally from this repo. The decision was made to link locally rather than too the live website to allow for local modifications of the content.