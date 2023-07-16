# stylemuse
This is a wildcard set for use with the Dynamics Prompts extension in Automatic1111

It is a work in progress, feel free to clone or download, but be aware that the structure might be in flux and names and directory structures might change between versions.

# INSTALLATION

You may just copy this repository and paste it into your stable diffusion dymanic prompts wildcard folder 

> stable-diffusion-webui/extensions/sd-dynamic-prompts/wildcard

# USAGE:

To use individual apparel, browse the apparel folder and select the apparel you want to use. Copy the contents in the Wildcards File field into your stable diffusion prompt.  Combine as necessary with other apparel.

Browse the lib folder and choose modifiers you want to use, such as colors, details, materials, etc.  Copy the contents in the Wildcards File field into your stable diffusion prompt.  Combine as necessary with other modifiers and apparel.

## PREMADE PROMPTS
Premade prompts are available in the prompts folder.  Copy the contents in the Wildcards File field into your stable diffusion prompt.  These prompts include combinations of the apparel and lib folders, for ease of use, you may copy individual like items from these prompt lists to edit and create your own mix.

The premade promtps include folders for males and females.  These will only pull pieces from the respective apparel folder.  The inclusive folder includes both male and female pieces into a single prompts, use them for more unexpected prompts.

## VARIABLES 
To use all items in a category in your prompt, copy any of the sub-options in the Wildcards, and replace the category with an asteriks as shown in the examples below.  This will add all items in that category to your prompt.  The first example below will add all colors hues to your prompt.  The second example will add all colors to your prompt.

> \_\_stylemuse/_lib/color/hues/*\_\_  

> \_\_stylemuse/_lib/color/*\_\_  

To create matching outfits, you can use the variables function in Dynamic Prompts, create a prompt with the following format by using the dollar sign and curly brackets.  Setting the variable is done using the equal sign, then setting the variable.  To use the variable in your prompt, use the dollar sign and curly brackets.  

The example below will create a variable called motif and set it to a random egyptian animal motif, what follows is the use of the motif variable.  The result will be a random egyptian animal motif and a random royal chest accessory.  Adding an exclamation point(!) after the variable will ensure that the variable is only set once per prompt, resulting in a matching outfit.

> ${motif!=\_\_stylemuse/_lib/motifs/ancient/egyptian/animals\_\_} ${motif} \_\_stylemuse/ancient/egyptian/accessory/chest/royal\_\_ {motif} \_\_stylemuse/ancient/egyptian/head/royal/*\_\_  

To randomize the variables, remove the exclamation point from the variable declaration as shown below.  This will randomize the variable every time it is used in the prompt, resulting in a random egyptian animal motif for the chest accessory and a different motif for the headwear. 

> ${motif=\_\_stylemuse/_lib/motifs/ancient/egyptian/animals\_\_} $ \_\_stylemuse/ancient/egyptian/accessory/chest/royal\_\_ {motif} \_\_stylemuse/ancient/egyptian/head/royal/*\_\_  

Keep in mind that token bleed is possible.  E.g. when prompting animal motifs the actual animal might appear in the image, or when prompting a color additional things in the image might take on the color.  In some situations using the BREAK keyword in between uses of the variables might help.  Also extensions such as regional prompt might help keep things in their place.

## NSFW
Note that some model checkpoints will tend toward not suitable for work images, especially when picking certain clothing items or only accessories.  If that is not what you want, then make sure to include the proper keywords in the negatives to try to prevent such outcomes.