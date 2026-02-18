# ===============================
# Advanced Python Library Makefile
# ===============================

PYTHON = python
PIP = pip

# Install project
install:
	$(PIP) install -e .
	$(PIP) install -r requirements-dev.txt

# Run tests
test:
	pytest -v

# Coverage
coverage:
	pytest --cov=my_advanced_lib --cov-report=term

# Run examples
run-basic:
	$(PYTHON) examples/basic_usage.py

run-advanced:
	$(PYTHON) examples/advanced_usage.py

run-decorators:
	$(PYTHON) examples/decorator_demo.py

run-all:
	$(PYTHON) examples/basic_usage.py
	$(PYTHON) examples/advanced_usage.py
	$(PYTHON) examples/decorator_demo.py

# Format code
format:
	black src tests
	isort src tests

# Type checking
typecheck:
	mypy src

# Clean cache
clean:
	find . -type d -name "__pycache__" -exec rm -r {} +
	rm -rf .pytest_cache .coverage htmlcov

# Full workflow
all: install test run-all coverage
