# Fridge‑to‑Fork Recipe Finder

This repository contains the source code and documentation for the
**Fridge‑to‑Fork Recipe Finder**, a project that builds on the
public [Tasty API](https://rapidapi.com/apidojo/api/tasty/) to
recommend recipes based on the ingredients you have on hand.  The
project also introduces **smart ingredient substitution** by
scraping substitution tables from *All Recipes* and *The Old
Farmer's Almanac*.  If you are missing an ingredient, the tool
will suggest alternatives so you can still prepare the meal.

## Project files

| File | Description |
| --- | --- |
| `Fridge to Fork Project Code.ipynb` | Jupyter Notebook version of the project.  This notebook includes the business case, objective statement, description of the smart substitution process and all of the code required to search the Tasty API, fetch recipe details and scrape substitution tables. |
| `Fridge to Fork Project Code (HTML Version).pdf` | A PDF (HTML export) of the notebook for easy viewing without Jupyter. |
| `fridge_to_fork.py` | A standalone Python script containing the same functionality as the notebook.  Run this from the command line to interactively search for recipes and request substitutions. |
| `README.md` | Documentation and instructions for the project. |

## Motivation

Meal planning can be difficult when you are missing ingredients or
have dietary restrictions.  While the Tasty API provides a rich
database of recipes with filters for vegetarian, keto or gluten‑free
diets, it doesn't offer help when an ingredient is unavailable.  This
project addresses that gap by integrating substitution data from
credible sources.  Users are guided through the process of selecting
a recipe, viewing its ingredients and instructions, and optionally
asking for a replacement when a specific ingredient isn't in their
pantry.

## Getting started

1. **Prerequisites:** Ensure you have Python 3 installed.  Then
   install the required dependencies:

   ```bash
   pip install requests pandas
   ```

2. **RapidAPI key:** Register on [RapidAPI](https://rapidapi.com/) and
   subscribe to the Tasty API.  Obtain your personal API key and
   replace the placeholder value of `API_KEY` in `fridge_to_fork.py`
   with your key.

3. **Running the notebook:** If you prefer the interactive notebook
   experience, open `Fridge to Fork Project Code.ipynb` in Jupyter
   Notebook or JupyterLab and run the cells in order.  The notebook
   contains explanatory text and code.

4. **Running the script:** To use the command‑line version, execute:

   ```bash
   python fridge_to_fork.py
   ```

   The script will prompt you to enter your dietary preference (for
   example *vegetarian*, *keto*, *gluten‑free* or `none`) and the
   ingredients in your fridge, separated by commas.  It then
   retrieves a list of recipe recommendations, including cook time and
   nutritional information.  After selecting a recipe, you will see
   the full ingredient list and instructions.  Finally, you can ask
   for an ingredient substitution suggestion.  The program will
   search the scraped substitution tables and return any matches.

## Notes

* The substitution functionality relies on web scraping of tables
  published by All Recipes and The Old Farmer's Almanac.  If those
  websites change their table structure, the scraping functions may
  need to be updated.
* This project is for educational purposes and is not affiliated
  with the Tasty API, All Recipes or The Old Farmer's Almanac.

## License

This repository is licensed under the MIT License.  See the
[`LICENSE`](LICENSE) file for details.
