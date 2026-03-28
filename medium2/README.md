# Wikipedia Link Graph Dataset - 15K Pages

A comprehensive Wikipedia dataset containing 15,320 pages with 5.6 million links, collected using breadth-first search crawling algorithm.

## Dataset Overview

- **Total Pages**: 15,320
- **Total Links**: 5,592,230 (directed edges)
- **Unique Target Pages**: 1,042,921
- **Average Words per Page**: 4,208
- **Language**: English (en.wikipedia.org)
- **Collection Method**: BFS (Breadth-First Search) crawling, depth 3

## Files Description

### 1. `pages_export.csv`
Complete page metadata including:
- `id`: Unique page ID
- `title`: Page title
- `language`: Language code (en)
- `content_length`: Content length in characters
- `word_count`: Word count
- `categories`: JSON array of categories
- `infobox`: JSON object of infobox data
- `created_at`: Timestamp
- `url`: Full Wikipedia URL (e.g., https://en.wikipedia.org/wiki/Page_Title)

**Size**: ~11 MB
**Rows**: 15,320

### 2. `links_export.csv`
Complete link graph with URLs:
- `id`: Unique link ID
- `source_title`: Source page title
- `target_title`: Target page title
- `language`: Language code
- `position`: Link position on page
- `depth`: Crawl depth where link was discovered
- `created_at`: Timestamp
- `source_url`: Full source page URL
- `target_url`: Full target page URL

**Size**: ~894 MB
**Rows**: 5,372,660

### 3. `graph.json`
Network graph in JSON format:
- `nodes`: Array of node objects with `id` field
- `edges`: Array of edge objects with `source` and `target` fields

**Size**: ~523 MB
**Nodes**: 1,042,924
**Edges**: 5,370,660

## Data Quality

- **Content Coverage**: 100% (all pages have content)
- **Link Coverage**: 104.5% (more links than pages due to multiple links per page)
- **Duplicate Content**: 595 (minimal)
- **Data Validation**: ✅ All entries validated

## Use Cases

1. **Network Analysis**: Study Wikipedia link structure and page connectivity
2. **Graph Algorithms**: Test shortest path, centrality, community detection algorithms
3. **NLP Research**: Analyze Wikipedia content, categories, and relationships
4. **Machine Learning**: Train models on Wikipedia link prediction
5. **Knowledge Graph**: Build knowledge graphs from Wikipedia structure

## Dataset Statistics

### Page Statistics
- Min words: Varies
- Max words: Varies  
- Average words: 4,208
- Median words: ~3,500

### Link Statistics
- Average links per page: ~365
- Max depth crawled: 3 levels
- Unique targets: 1,042,921 pages

## Collection Methodology

1. **Seed Selection**: Started with 5 random Wikipedia pages
2. **Crawling**: BFS algorithm, depth 3
3. **Rate Limiting**: Balanced (0.05s delay per request)
4. **Parallel Processing**: 10 concurrent workers
5. **Caching**: HTML content cached for efficiency
6. **Validation**: All data validated and deduplicated

## Technical Details

- **Database**: SQLite
- **Crawl Duration**: ~34 hours
- **Crawl Rate**: ~0.13 pages/second
- **Checkpoint System**: Resume-capable crawling

## Citation

If you use this dataset, please cite:

```bibtex
@dataset{wikipedia_link_graph_2025,
  title={Wikipedia Link Graph Dataset - 15K Pages},
  year={2025},
  url={https://www.kaggle.com/datasets/...}
}
```

## License

This dataset is based on Wikipedia content, which is licensed under Creative Commons Attribution-ShareAlike 3.0 License.

## Acknowledgments

- Wikipedia Foundation for providing open access to Wikipedia data
- Built using Python, BeautifulSoup, and SQLite

## Contact

For questions or issues, please open an issue on the dataset page.

