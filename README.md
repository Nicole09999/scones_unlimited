
# Scones Unlimited ML Workflow

## Overview

This project demonstrates the construction of a machine learning workflow using Amazon SageMaker. The goal is to build an automated system for classifying images of scones, muffins, and other related items, enabling "Scones Unlimited" to enhance their product offerings by identifying and categorizing baked goods accurately.

## Architecture

The architecture of this project includes several key components:

1. **AWS Lambda Functions**:
   - **Lambda 1**: Fetches an image from an S3 bucket and converts it into a base64 string.
   - **Lambda 2**: Sends the image to a deployed SageMaker model for inference.
   - **Lambda 3**: Evaluates the inference result against a predefined confidence threshold.

2. **AWS Step Functions**: 
   - Orchestrates the entire workflow by managing the sequence of Lambda functions.
   - Ensures that the image data is passed correctly between functions and that the inferences meet the required confidence level.

3. **Amazon SageMaker**:
   - Hosts the machine learning model used for image classification.

   - Provides the API endpoint for real-time inference during the workflow.

## Workflow Diagram

Below is a placeholder for the image of the AWS Step Function workflow. This diagram illustrates the sequence and interaction between the various components in the system.

(![Screenshot 2024-08-12 201318](https://github.com/user-attachments/assets/f6b176ac-b66a-4da9-8c49-5bdbbd7143dd))



## Getting Started

### Prerequisites

- An AWS account with access to Lambda, S3, SageMaker, and Step Functions.
- Basic understanding of Python and AWS services.
- IAM roles with sufficient permissions to invoke SageMaker endpoints and manage S3 buckets.

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/scones-unlimited-ml-workflow.git
   ```

2. Navigate to the project directory:
   ```bash
   cd scones-unlimited-ml-workflow
   ```

3. Install necessary dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Deploying the Workflow

1. **Setup S3 Bucket**: Upload the test images to your S3 bucket.

2. **Deploy SageMaker Model**: Train and deploy the machine learning model on SageMaker. Ensure the endpoint is active and accessible.

3. **Configure Lambda Functions**: Deploy the three Lambda functions provided in the `lambda_functions` directory. Update the configurations as per your S3 bucket and SageMaker endpoint.

4. **Create Step Function**: Define the Step Function workflow using the `state_machine_definition.json` file. This will orchestrate the execution of your Lambda functions.

5. **Run the Workflow**: Execute the Step Function with appropriate input data, and monitor the results in the AWS Management Console.

### Usage

1. Trigger the Step Function with an S3 key as input.
2. The system will automatically:
   - Fetch the image.
   - Perform inference using the SageMaker model.
   - Validate the results against the confidence threshold.

3. Review the results in the AWS Step Functions console.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This `README.md` file provides a comprehensive guide to your project, with a placeholder for the image that you can replace once you have it.
