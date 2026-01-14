# development workflows

- volume and speed of AI output
	- natural throttles
		- human need/ability to understand
		- human need/ability to validate
- speed of dev delivery highlights pre/post-development tasks
    - story creation
    - story testing/validation
- basic situation
    - concern with value is constant
    - delivery speed is increasing
    - how do you 
	    - ensure quality does not decrease
	    - developers are not idle
    - software saugage making (with due allowance for varients)
        - define > design > implement > test > deliver > test > use

## options
- use AI to accelerate story creation & post-delivery testing
    - still have burden of human verification
        - maybe only AI for story creation?
- have different roles/people create stories and test post-delivery
    - not ideal because of increased hand-off friction
    - increased risk that mose team members lose 'the why'
- move developers across different teams: "plate spinning"
    - not ideal because devs can lose 'the why'

## workflow scenario 1

1. **Story Creation**: TPM manages backlog and creates story
2. **Design Phase**: Designer creates design based on story
3. **Tech Spec Phase**: Developer creates technical specification using story and design
4. **Verification**: All three roles verify the tech spec with possible outcomes:
   - **Approved**: Proceed to implementation
   - **Story Revision Needed**: Loop back to TPM to revise story, then through design and tech spec
   - **Design Revision Needed**: Loop back to Designer to revise design, then tech spec
5. **Implementation**: Developer implements and verifies the code
6. **Testing**: TPM tests the final implementation

### Feedback Loops

The diagram includes feedback loops that represent real-world scenarios where:
- Technical constraints discovered during spec creation require story changes
- Design elements need refinement based on technical feasibility
- Iteration happens before moving to implementation

## resources

- [ai-workflows](https://github.com/sdbroscious/ai-resources/tree/main/dev-of-future/resources/development-flows/ai-workflows)
- [spec-driven-design](https://github.com/sdbroscious/ai-resources/tree/main/dev-of-future/resources/development-flows/spec-driven-dev)