# Task Processor API

This API offers a service to process various tasks using an advanced agent-based system. It utilizes `autogen` with two specialized agents (Agent 1 and Agent 2) to handle and resolve complex tasks.

## Getting Started

### Prerequisites

- Python 3.9 or higher
- Docker (optional for deploying in a containerized environment)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/example/flask-task-processor.git
   cd flask-task-processor
   ```

2. (Optional) Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # For Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the API

#### Direct Execution:

   ```bash
   python app.py
   ```

   The service will be available on port 5001.

#### Using Docker:

1. Build the Docker image:
   ```bash
   docker build -t flask-task-processor .
   ```

2. Start the Docker container:
   ```bash
   docker run -p 5001:5001 flask-task-processor
   ```

## Usage

To use the service, send a POST request to `/submit_task` with a JSON payload:

```json
{
    "task": "YOUR_TASK_HERE",
    "prompt_agent_1": "PROMPT_FOR_AGENT_1",
    "prompt_agent_2": "PROMPT_FOR_AGENT_2",
    "api_key": "YOUR_API_KEY",
    "model": "MODEL_NAME"
}
```

You will receive a request ID in response. To check the task's status and result, send a GET request to `/get_result/<request_id>`.

## Contributing

We welcome contributions. For significant changes, please open an issue first to discuss your ideas.

## License

This project is under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.