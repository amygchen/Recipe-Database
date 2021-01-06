# Recipe-Database
## This database compiles information about different recipes found around the web. It keeps track of recipe ingredients, authors, reviews, and reviewers.

RDM:



## Queries

__Select Recipes that take less than 30 minutes:__

'''
SELECT recipeName, (prepTimeMin + cookTimeMin) AS totalTime
FROM GeneralRecipe
WHERE (prepTimeMin + cookTieMin) < 30
ORDER BY (prepTimeMin + cookTimeMin);
'''

__Select recipes that have _x_ ingredients:__

'''
SELECT recipeName
FROM GeneralRecipe INNER JOIN 
    (Ingredients INNER JOIN GeneralRecipeHasIngredients ON Ingredients.ID = GeneralRecipeHasIngredients.i	ngredientsID) ON GeneralRecipe.ID = GeneralRecipeHasIngredients.generalRecipeID
GROUP BY recipeName
HAVING MAX(dairy = FALSE) AND 	MAX(meat = FALSE) AND 	MAX(ingredientName 	NOT LIKE 	'egg');
'''
