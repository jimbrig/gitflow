## Nomenclature
### General rule
The variable you name should **explicitly** reflect what the variable is representing. The goal is to avoid mistake by making false assumption on the value of a variable

Examples :
1. first_name (the first name of a person)
2. account (an account)
3. next_line_to_delete (the next line to be deleted)

Correct variable names should be short. Avoid turning sentences into variable name. Try to only use key words to keep the name short if necessary

Special types of variable are bound by this rule but need to have a prefix/postfix to give more information on the type of the variable
### Boolean
Prefix the name with is_ or has_

Examples:
1. is_redeemed
2. is_admin
3. is_changed
4. has_invoices
5. has_generated_moves
### Many2one
Post-fix the name with _id

Examples:
1. product_id
2. account_id
### Many2many and one2many
Post-fix the name with _ids

Examples:
1. product_ids
2. account_move_line_ids
