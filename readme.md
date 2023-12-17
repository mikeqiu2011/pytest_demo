# pytest demo

## pre
    pip install -r requirements.txt
    pip install cards_proj/

## run
    
### setup/ teardown:
    pytest --setup-show ch3/test_count.py
    pytest --setup-show ch3/test_mod_scope.py

### conftest
    pytest --setup-show ch3/a/test_count.py
    pytest --fixtures
    pytest --fixtures-per-test ch3/a/test_count.py::test_empty


### fixture depend on other fixture with different scope
    ch3/b/conftest.py

### calculate test duration
    pytest -s ch3/test_autouse.py
    
### builtin fixtures
    ch4/conftest.py

### parameterize
    pytest -v ch5/test_func_param.py::test_finish_simple

### markers
    pytest -ra ch6/builtins/test_skip.py
    pytest -ra -m exception ch6/reg/test_start.py
    pytest -ra -v -m "finish and exception" ch6/multiple/
    pytest -ra -v ch6/combined/test_num_cards.py

### pytest settings
    cat ch8/project/pytest.ini

### test coverage
    pytest --cov=cards --cov-report=term-missing ch7
    pytest --cov=cards --cov-report=html ch7
    # pragma: no cover

## ref
    https://pragprog.com/titles/bopytest2/python-testing-with-pytest-second-edition/