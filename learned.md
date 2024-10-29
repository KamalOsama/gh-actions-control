- default behavior for workflows
  - If one job fails the jobs that depends on it stops (needs)

- if
  - if the condition of if is met, step is executed

- failure() ==> look in slides

- cache
  - cache jobs has an output (cache-hit)
  - if there is a cache to the specified step, cache-hit returns true

- continue-on-error
  - make the job continue if a step fails

- conclusion vs outcome
  - outcome evaluates the outcome before continue-on-error executes, outputs the value before the step continues if an error happens, Thus might return false due to step failing
  - conclusion evaluates the outcome after continue-on-error executes, outputs the value after the step continues if an error happens, Thus will always return true,Only if there is a syntax, network, etc.. errors

- matrix
  - Default: If one value in the matrix failed, The other jobs wich uses the other values will stop
  - To unable this, Use continue-on-error on the job level

- include & exclude
  - include: include a combination that is not in the matrix to be executed
  - exlude: exludes a certain combination inthe matrix to be executed

- Reusable workflows
  - to make it reusable ==> `on: workflow_call`
  - to call it ==> `./.github/workflows/{filename}`

- inputs:
  - it's the paramters of the workflow
  - to provide paramters we use `with:`
  - inputs can be secrets, use `secrets:` to declare secret parameters