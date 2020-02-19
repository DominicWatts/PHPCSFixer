# docker image with php-cs-fixer

[Docker_Hub](https://hub.docker.com/r/domw/php-cs-fixer)

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

### Magento 2 ruleset

    docker run --rm -v $PWD:/code domw/php-cs-fixer php-cs-fixer fix --rules={"@PSR2":true,"array_syntax":{"syntax":"short"},"concat_space":{"spacing":"one"},include,new_with_braces,no_empty_statement,no_extra_consecutive_blank_lines,no_leading_import_slash,no_leading_namespace_whitespace,no_multiline_whitespace_around_double_arrow,no_multiline_whitespace_before_semicolons,no_singleline_whitespace_before_semicolons,no_trailing_comma_in_singleline_array,no_unused_imports,no_whitespace_in_blank_line,object_operator_without_whitespace,ordered_imports,standardize_not_equals,ternary_operator_spaces} --using-cache=no ./path/to/code
