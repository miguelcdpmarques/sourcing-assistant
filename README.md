# Sourcing Agent

An AI-powered recruiter message generation system that creates personalized, compelling outreach messages for candidate recruitment.

## What It Does

This tool orchestrates multiple AI agents to analyze candidate profiles, job descriptions, and company information, then generates highly personalized recruiter messages. The system:

1. **Researches** candidate backgrounds, company details, and job requirements
2. **Identifies** key motivators and alignment points
3. **Writes** natural, human-sounding recruiter messages
4. **Refines** tone, grammar, and flow for maximum impact

The output is 3 ready-to-send recruiter messages, each taking a different angle to maximize response rates.

## Repository Structure

```
sourcing-agent/
├── data/                          # Input data folder
│   ├── candidate-info.md          # Candidate profile information
│   ├── candidate-resume.pdf       # Candidate resume
│   ├── company-info.md            # Target company details
│   └── job-info.md                # Job description and requirements
├── .claude/
│   └── agents/                    # AI agent definitions
│       ├── research-agent.md      # Analyzes data and identifies motivators
│       ├── recruiter-message-writer.md  # Drafts personalized messages
│       └── recruiter-redactor.md  # Perfects tone and grammar
├── orchestrator.md                # Main orchestration agent
└── output/                        # Generated messages
    ├── message-1.md
    ├── message-2.md
    └── message-3.md
```

## How to Run

### Prerequisites

- [Claude Code CLI](https://claude.com/claude-code) installed
- Candidate and job data populated in the `data/` folder

### Running the System

1. **Prepare your data**: Add the following files to the `data/` folder:
   - `candidate-info.md` - Candidate details (LinkedIn profile, background, etc.)
   - `candidate-resume.pdf` - Candidate's resume
   - `company-info.md` - Target company information
   - `job-info.md` - Job description and requirements

2. **Launch Claude Code**:
   ```bash
   # Navigate to the project directory
   cd sourcing-agent

   # Start Claude Code CLI
   claude-code
   ```

3. **Run the orchestrator**:
   In the Claude Code interface, simply type:
   ```
   run the orchestrator
   ```

   Claude Code will automatically:
   - Invoke the **research-agent** to analyze candidate/company/job data
   - Pass insights to the **recruiter-message-writer** to draft 3 messages
   - Send each draft through the **recruiter-redactor** for polishing
   - Save the final messages to the `output/` folder

4. **Check the output**: Generated messages will be saved in the `output/` folder as:
   - `message-1.md`
   - `message-2.md`
   - `message-3.md`

## Output

Each generated message includes:
- A compelling subject line
- Personalized content referencing candidate-specific details
- Clear value proposition aligned with candidate motivators
- Natural, conversational tone
- Call-to-action with easy next steps

## How It Works

The orchestrator coordinates three specialized agents:

1. **Research Agent**: Analyzes all input data to identify:
   - Candidate skills, experience, and career trajectory
   - Key motivators based on profile patterns
   - Strongest alignment points between candidate and opportunity
   - Personalization angles for maximum engagement

2. **Message Writer**: Creates 3 different message variations:
   - Each message uses a different motivational angle
   - Acknowledges candidate's current situation
   - Keeps messages short (4-6 sentences)
   - Maintains authentic, non-salesy tone

3. **Redactor**: Polishes final messages for:
   - Grammar and punctuation
   - Flow and readability
   - Tone consistency
   - Natural transitions

## Customization

To customize the agents' behavior, edit the agent files in `.claude/agents/`:
- Modify prompts to change message style or focus
- Adjust message length requirements
- Add/remove specific evaluation criteria
