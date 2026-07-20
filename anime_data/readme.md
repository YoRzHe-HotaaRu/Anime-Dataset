# OtakuDB

![Logo](https://i.ibb.co/HLrBpDzR/otakudb-logo-alt.png)

## Overview

This dataset offers a comprehensive look at anime series from MAL, covering rankings, ratings, episode counts, genres, studios, and more. Whether you're a researcher, data scientist, or anime fan, this structured data can help with analysis, building recommendation systems, or exploring trends in the anime world.

## Dataset Information

### Features

The dataset includes the following information for each anime:

| Column        | Description                             |
| ------------- | --------------------------------------- |
| Rank          | The anime's rank on MyAnimeList         |
| Title         | Original title of the anime             |
| English Title | English translated title (if available) |
| URL           | Link to the anime's page on MyAnimeList |
| Image URL     | Link to the anime's cover image         |
| Score         | Rating score (out of 10)                |
| Users Rated   | Number of users who rated the anime     |
| Episodes      | Total number of episodes                |
| Genres        | Categories the anime belongs to         |
| Studios       | Studio(s) that produced the anime       |
| Synopsis      | Brief description of the anime's plot   |
| Popularity    | Popularity ranking                      |
| Ranked        | Official rank based on score            |

### Statistics

- Dataset Last Update: March 29, 2025
- Total entries: 13900
- Highest rated anime: Sousou no Frieren (9.31)
- Most popular anime: Fullmetal Alchemist: Brotherhood (2,202,757 ratings)

## Usage Examples

### Python Example

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
anime_df = pd.read_csv('anime_dataset.csv')

# Basic exploration
print(f"Dataset shape: {anime_df.shape}")
print(f"Top 5 highest rated anime:\n{anime_df.sort_values('Score', ascending=False).head()}")

# Plot distribution of scores
plt.figure(figsize=(10, 6))
plt.hist(anime_df['Score'], bins=20)
plt.title('Distribution of Anime Scores')
plt.xlabel('Score')
plt.ylabel('Count')
plt.show()

# Analyze genres
all_genres = []
for genres in anime_df['Genres'].str.split(', '):
    if isinstance(genres, list):
        all_genres.extend(genres)

genre_counts = pd.Series(all_genres).value_counts()
print("Most common genres:")
print(genre_counts.head(10))
```

> [!WARNING]
> This dataset has not been cleaned or preprocessed. It may contain duplicate entries, missing values, inconsistencies, or formatting issues, its advised to perform necessary data cleaning before using it for analysis, machine learning, or other applications.

## Support Me

If you find this dataset useful, consider giving it a star ⭐! It helps others discover it too.

## License

This dataset is released under the CC-BY-SA 4.0 [license](LICENSE.md). This means you:

- Must give appropriate credit
- Must indicate if changes were made
- May distribute your contributions under the same license

## Citation

If you use this dataset in your research or project, please cite:

```
@dataset{OtakuDB,
  author = {Debojit Mitra},
  title = OtakuDB,
  year = 2025,
  publishedOn = {GitHub & Kaggle},
  url = https://github.com/Debojit-mitra/OtakuDB
}
```

## Acknowledgments

- Thanks to the anime community for maintaining ratings and information

## Contact Information

For questions, suggestions, or collaborations, please:

- Open an issue on GitHub
- Contact me via: [Email](mailto:bunny16github@gmail.com)
