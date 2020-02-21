# docker image with php-cs-fixer

[Docker_Hub](https://hub.docker.com/r/domw/php-cs-fixer)

## php-cs-fixer-configurator

https://mlocati.github.io/php-cs-fixer-configurator/

## Compilation

    docker login

    docker build -t domw/php-cs-fixer:latest ./

    docker push domw/php-cs-fixer:latest

    docker build -t domw/php-cs-fixer:7.1-cli ./

    docker push domw/php-cs-fixer:7.1-cli 

## Test

    docker-compose run --rm pcf php-cs-fixer

    docker-compose run --rm pcf php-cs-fixer --version

## Usage
    
    docker pull domw/php-cs-fixer

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer --version
    
    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules=@PSR2 ./path/to/code

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules=@PSR2 --using-cache=no ./path/to/code
    
    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --verbose --using-cache=no --rules=phpdoc_no_package,ordered_imports ./path/to/code

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules=@PSR2 --verbose --using-cache=no ./path/to/code

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules=@PSR2 --verbose --using-cache=no --allow-risky=yes ./path/to/code    

### Magento 2 ruleset

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules='{"@PSR2":true,"array_syntax":{"syntax":"short"},"concat_space":{"spacing":"one"},"include":true,"new_with_braces":true,"no_empty_statement":true,"no_extra_consecutive_blank_lines":true,"no_leading_import_slash":true,"no_leading_namespace_whitespace":true,"no_multiline_whitespace_around_double_arrow":true,"no_multiline_whitespace_before_semicolons":true,"no_singleline_whitespace_before_semicolons":true,"no_trailing_comma_in_singleline_array":true,"no_unused_imports":true,"no_whitespace_in_blank_line":true,"object_operator_without_whitespace":true,"ordered_imports":true,"standardize_not_equals":true,"ternary_operator_spaces":true,"phpdoc_no_package":true}' --using-cache=no --allow-risky=yes --verbose ./path/to/code

### Custom ruleset

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules='{"@PSR2":true,"array_syntax":{"syntax":"short"},"concat_space":{"spacing":"one"},"ordered_imports":true,"blank_line_after_opening_tag":true,"comment_to_phpdoc":true,"ereg_to_preg":true,"fully_qualified_strict_types":true,"include":true,"linebreak_after_opening_tag":true,"logical_operators":true,"no_blank_lines_after_phpdoc":true,"no_empty_comment":true,"no_empty_phpdoc":true,"no_empty_statement":true,"no_extra_consecutive_blank_lines":true,"no_leading_import_slash":true,"no_leading_namespace_whitespace":true,"no_php4_constructor":true,"no_unused_imports":true,"no_useless_else":true,"no_useless_return":true,"normalize_index_brace":true,"phpdoc_add_missing_param_annotation":true,"phpdoc_annotation_without_dot":true,"phpdoc_indent":true,"phpdoc_inline_tag":true,"phpdoc_no_access":true,"phpdoc_order":true,"phpdoc_return_self_reference":true,"phpdoc_scalar":true,"phpdoc_single_line_var_spacing":true,"phpdoc_to_comment":true,"phpdoc_trim":true,"phpdoc_types_order":true,"phpdoc_types":true,"phpdoc_var_without_name":true,"protected_to_private":true,"short_scalar_cast":true,"standardize_not_equals":true,"string_line_ending":true,"ternary_operator_spaces":true,"whitespace_after_comma_in_array":true,"phpdoc_no_package":true}' --using-cache=no --allow-risky=yes --verbose ./path/to/code
