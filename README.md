![Art Institute of Chicago](https://raw.githubusercontent.com/Art-Institute-of-Chicago/template/master/aic-logo.gif)

# Public API data

Founded in 1879, the [Art Institute of Chicago](https://www.artic.edu) is one of the world’s major museums, housing an extraordinary collection of objects from across places, cultures, and time. We are also a place of active learning for all—dedicated to investigation, innovation, education, and dialogue—continually aspiring to greater public service and civic engagement.

We provide access to all of our public data through a single, unified [API](https://api.artic.edu/docs). This API is powered by a [data hub](https://github.com/art-institute-of-chicago/data-aggregator), a system our engineers built to collect public information from a number of different internal systems. In our API, you can find data about our collections, digital publications, in-gallery interactives, mobile apps, shop products, events, and more.

For a number of reasons, users might want to have a copy of our entire dataset to work with locally, instead of querying our API. We've made it easy to obtain this dataset by providing a full data dump of our API here, via this repo.


## Where is the full dataset?

The full dataset is too large to host on GitHub. This repository serves as a preview of the dataset by offering 10 sample records for each endpoint in the API. You can download the full dataset here:

https://artic-api-data.s3.amazonaws.com/artic-api-data.tar.bz2

The contents of that link are updated on the same schedule as this GitHub repository. At the time of writing, this dataset is about 75 MB compressed but takes up about 1.75 GB on disk after being extracted.


## What's in the dataset?

The [json](json) folder contains a number of subfolders, each of which represents a different endpoint in our API. Within each of these folders, you'll find a series of files named `{id}.json`, where `{id}` represents the unique identifier of the record. Each file's contents contains exactly what you can obtain from our API for that record.

Please consult our [API documentation](https://api.artic.edu/docs) for more information about fields and endpoints.

The `json` folder also contains [config.json](json/config.json) and [info.json](json/info.json). These files contain the `config` and `info` blocks that are present at the bottom of each API response. The `config` block is the same for all API responses, but each endpoint has a unique `info` block. As such, `info.json` contains all of the info blocks, keyed by endpoint.

The [getting-started](getting-started) folder contains smaller samples of our data, meant for users who might not want our entire dataset:

 * [allArtworks.jsonl](getting-started/allArtworks.jsonl) contains all of our artworks with a few key fields in [JSONL](http://jsonlines.org/) format.
 * [someArtworks.csv](getting-started/someArtworks.csv) contains about 300 of our top artworks with the same fields in CSV format.

Generally, we encourage users to write their programs against the full dataset, since this sample data does not capture the edge-cases and nuances of the full dataset. Additionally, our API does not provide data in CSV format, so anything that you build using the CSV file will be difficult to scaffold up to our regular API dataset.

Images are not included and are not part of the dataset. For more details on how to use images of artworks in the Art Institute of Chicago’s collection, please visit our [open access](https://www.artic.edu/open-access) page.

As this data is automatically refreshed on a monthly basis, so please be sure to regularly update your copy of the dataset to ensure you are using the best available information.


## Contributing

Because updating this data has been automated, we only accept pull requests for changes to documentation—and we encourage your contributions. Please fork this repository and make your changes in a separate branch.

```bash
# Clone the repo to your computer
git clone git@github.com:art-institute-of-chicago/api-data.git

# Enter the folder that was created by the clone
cd api-data

# Start a feature branch
git checkout -b feature/good-short-description

# ... make some changes, commit your code
yourfavoritetexteditor README.md
git add .
git commit -m 'Add a clear and concise commit message'

# Push your branch to GitHub
git push origin feature/good-short-description
```

Then on GitHub, create a Pull Request to merge your changes into our `master` branch.

This project is released with a Contributor Code of Conduct. By participating in this project you agree to abide by its [terms](CODE_OF_CONDUCT.md).

We welcome bug reports and questions under GitHub's [Issues](issues). For other concerns, you can reach our engineering team at [engineering@artic.edu](mailto:engineering@artic.edu)


## Licensing

Note that all content may have different licensing terms. Please be mindful of the `info.license_text` and `info.license_links` fields within each JSON data file. These notices refer to the metadata that each file represents, they do not apply to images and media which may have different licensing terms.
