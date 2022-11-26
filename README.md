<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<h3 align="center">A journal recommender for the submission of your scientific manuscript</h3>

  <p align="center">
    Based on the cosine similarity between BERT-encoded journal scopes and a user-provided abstract
    <br />
    <a href="https://github.com/masadeghi/journal_finder"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/masadeghi/journal_finder/issues">Report Bug</a>
    ·
    <a href="https://github.com/masadeghi/journal_finder/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#future-steps">Future Steps</a></li>
      </ul>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

The goal of this project is to build a journal recommender for submission of a scientific manuscript. The recommendations are based on similarities between the scope of the journals and the user-provided abstract of a manuscript. To achieve this, two steps have been taken:

**1. scimagojr_scrape.ipynb script:** I scraped scimagojr.com to extract the scope of each journal from it's dedicated webpage on [scimagojr.com](https://www.scimagojr.com/journalrank.php) and stored these scopes in a separate dataset for each subject category: Biochemistry, Genetics and Molecular Biology / Immunology and Microbiology / Medicine / Neuroscience / Pharmacology, Toxicology, and Pharmaceutics.  

**2. journal_finder.ipynb script:** I used a BERT model pretrained on MEDLINE/Pubmed texts which is available on [TensorFlow Hub](https://tfhub.dev/google/experts/bert/pubmed/2) to convert the journal scopes and the user-provided abstract into feature vectors. Then I used cosine similarity values between these vectors to find the most similar scopes
  to the provided abstract.

The scraped scopes can be viewed in the [scraped_from_scimago directory](https://github.com/masadeghi/journal_finder/tree/main/scraped_from_scimago), and their encodings (BERT pooled outputs) are available in the [journal_scope_encodings](https://github.com/masadeghi/journal_finder/tree/main/journal_scope_encodings) directory as .pkl files.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Future Steps
In its current form, the recommendations have a lot of room for improvement! The next step I'm working on is to retrain and finetune the BERT model using journal_scope/abstract pairs from previously published articles on Pubmed to improve model performance.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Built With

* Python v3.7.15
* TensorFlow v2.8.0

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

If you want to test the final functionality (journal recommendation system), import the .pkl dictionaries to the journal_finder.ipynb script and skip to the
"Define function that computes similarity ..." section.

### Installation

No installation is required. Just open the scripts in Google Colab and you're good to go.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Finding suitable journals for your manuscript can be a tedious and time-consuming process, especially if you're new to a field or your manuscript was rejected by your first- and second-choice journals. Having a powerful recommender can save up a lot of time in this regard.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the Apache 2.0 License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Amin Sadeghi - masadeghi6@gmail.com

Project Link: [https://github.com/masadeghi/journal_finder](https://github.com/masadeghi/journal_finder)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/masadeghi/journal_finder.svg?style=for-the-badge
[contributors-url]: https://github.com/masadeghi/journal_finder/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/masadeghi/journal_finder.svg?style=for-the-badge
[forks-url]: https://github.com/masadeghi/journal_finder/network/members
[stars-shield]: https://img.shields.io/github/stars/masadeghi/journal_finder.svg?style=for-the-badge
[stars-url]: https://github.com/masadeghi/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/masadeghi/journal_finder.svg?style=for-the-badge
[issues-url]: https://github.com/masadeghi/journal_finder/issues
[license-shield]: https://img.shields.io/github/license/masadeghi/journal_finder.svg?style=for-the-badge
[license-url]: https://github.com/masadeghi/journal_finder/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/mohammad-amin-sadeghi-md/
