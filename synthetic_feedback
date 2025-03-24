# Multi-Perspective Synthetic Feedback Generator

This tool generates diverse synthetic feedback for animal advocacy content by simulating perspectives from both human and non-human animals. It's designed to create a rich, multi-perspective dataset for training machine learning models that can predict how content will be received by different audiences. We used this script (augmented with real human feedback data from animal advocates) to create the [Animal Alignment Feedback Dataset](https://huggingface.co/datasets/open-paws/animal_alignment_feedback), which in turn was used to train multiple [ranking models for animal advocacy](https://huggingface.co/collections/open-paws/ranking-models-67b94c024535b84d0b73648b).

## Overview

The generator creates synthetic personas representing a wide range of perspectives:

- **Human personas** with diverse demographics, beliefs, and advocacy approaches
- **Non-human animal personas** across species and living situations (wild, farmed, companion, etc.)

These personas evaluate content (text, images, dialogues, websites) across multiple dimensions relevant to animal advocacy effectiveness.

## Key Features

- **Demographic Diversity**: Generates human personas with realistic distributions of age, gender, ethnicity, education, income, political views, and religious beliefs
- **Species Diversity**: Creates non-human personas across hundreds of species with population-weighted representation
- **Multi-dimensional Evaluation**: Each persona rates content on various dimensions including effect on animals, trustworthiness, emotional impact, and more
- **Multi-language Support**: Can generate explanations in 45+ languages while keeping ratings consistent
- **Content Flexibility**: Processes text, dialogues, images, and web pages

## How It Works

1. **Persona Generation**: Creates thousands of synthetic personas with detailed characteristics
2. **Content Processing**: Retrieves content from input bucket (text, images, websites)
3. **Perspective Taking**: Uses LLMs to evaluate content from each persona's unique viewpoint
4. **Structured Feedback**: Outputs standardized JSON with ratings and explanations. These outputs follow the Label Studio format used on our [human feedback collection](https://github.com/Open-Paws/Human-Feedback-Label-Studio) project.
5. **Cross-species Empathy**: Non-human personas provide insights on how content affects their species and others

## Technical Implementation

- Uses Google Cloud Storage for input/output
- Leverages Vertex AI's Gemini 1.5 Pro for perspective-taking
- Implements retry logic for API resilience
- Processes web content with BeautifulSoup
- Handles various media types (text, images, HTML)

## Usage

1. Set `DRYRUN = False` for production use or `True` for testing
2. Configure your Google Cloud project and bucket details
3. Place input content as JSON files in the input bucket
4. The script processes files and outputs synthetic feedback to the output bucket

## Ethical Considerations

This tool is designed specifically for animal advocacy content evaluation. The synthetic personas represent a wide range of perspectives to ensure diverse feedback, but all maintain a baseline recognition that animal exploitation causes harm, regardless of their personal choices or beliefs.

## Output Format

The tool generates structured JSON output compatible with annotation platforms, including:

- Ratings (1-5) across multiple dimensions
- Detailed explanations from each persona's perspective
- Complete persona metadata for analysis

## Population Weighting

The distribution of personas is designed to reflect:

1. Global human demographic distributions (for human personas)
2. Relative population sizes and human impact levels (for non-human personas)

This ensures the synthetic dataset represents both common and marginalized perspectives in proportions that reflect real-world conditions.

We also used a completely randomised version of this script without any weighting for demographic distributions to augment our dataset in order to add diversity.
