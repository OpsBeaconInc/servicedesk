# Workflow

Workflows assist you in organizing and automating your tasks. You can execute different commands in a row, even depending on specified conditions. A workflow can consist of 4 types of steps:

## 1. Run-Command

Executes selected command-connection pair with entered arguments of the command.

Example:

![RunCommand](/docs/images/runcommand.png)

```json
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```

## 2. Run-Parser

Parses the response of a selected step to provide the desired output.

Run parser contains two fields. We specify the response of a step in **input** field to parse, and desired item from parsed response in **output** field.

Example:

![RunParser](/docs/images/runparser.png)

Run-parser parses the response of first step here, and gives value of "completed" field from the response as output. In our case, response of this step is "false".

## 3. Run-Condition

Compares two values, which can be user input or from previous steps. If the condition is satisfied, the flow continues with a new branch of this step before continuing the rest.

The "Run condition" comprises four fields: **reference** and **comparison values** used in the comparison, **type** indicating whether the values are string, boolean, or integer, and **operators** to choose the desired kind of operator. Operators differ depending on the value type.

Example:

![RunCondition](/docs/images/runcondition.png)

Run condition checks whether the response of second step equals the string ***false***. If it does, then workflow evaluates the content inside the box of the run condition step before before proceeding with the remaining workflow steps. So, if the response is ***false*** the workflow prints ***The condition is met!*** first, followed by ***End of the workflow***. Otherwise, only ***End of the workflow*** is printed.

## 4. Run-Print

Prints a intended response simply.

The "Run print" step has an **input** field that accepts text from the user to print. Additionally, values from other steps can be passed here for printing.

You can see an example of this step in the sample provided above.
