# Word Clouds
A word cloud is a way to display a collection of words as a cloud-shaped image, where the size of each word represents its frequency or importance. Word clouds are often used to visualize text data, such as customer reviews, social media posts, or news articles, to quickly understand the most common words or themes in the data.

This folder contains examples and explanations of how to create word clouds in Python using the wordcloud library. The examples will cover basic word clouds, as well as how to customize the appearance of the clouds.

## Creating a basic word cloud
To create a basic word cloud, you need to provide the text data for the cloud, and then call the WordCloud function to create the cloud. Here's an example:


```Python
from wordcloud import WordCloud
import matplotlib.pyplot as plt

# Create some sample text
text = "This is a sample text for creating a basic word cloud. It can be a customer review, social media post, or news article. The most common words or themes in the data will be shown in the word cloud."

# Create the word cloud
wordcloud = WordCloud().generate(text)

# Show the word cloud
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis("off")
plt.show()

```
![1](https://user-images.githubusercontent.com/63750425/214024870-70423861-4e02-495e-96bd-6903f910e0b5.png)

This will create a basic word cloud with the text you provided. The words in the cloud will be shown in different sizes based on their frequency in the text.

## Customizing the appearance
You can customize the appearance of the word cloud by modifying the properties of the cloud, such as the background color, the font, or the color of the words. Here's an example:

```Python
from wordcloud import WordCloud
import matplotlib.pyplot as plt

# Create some sample text
text = "This is a sample text for creating a basic word cloud. It can be a customer review, social media post, or news article. The most common words or themes in the data will be shown in the word cloud."


# Create the word cloud
wordcloud = WordCloud(background_color='white', font_path='arial.ttf', 
                      max_words=50, contour_color='black', contour_width=3).generate(text)

# Show the word cloud
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis("off")
plt.show()

```
![2](https://user-images.githubusercontent.com/63750425/214024891-0602414e-5a18-4bf4-92f9-bb238a7b5c4f.png)


In this example, we passed background_color='white' to set the background color of the cloud to white, font_path='arial.ttf' to set the font to Arial, max_words=50 to limit the number of words in the cloud to 50, contour_color='black' and contour_width=3 to add a black border around the words with width of 3 pixels.

You can also use the generate_from_frequencies method to generate a word cloud from a dictionary of word frequencies, and use the mask parameter to create a word cloud in the shape of an image.

