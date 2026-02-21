# Report Unit Tests Skill

Ensure valid unit tests are written for any code that generates reports in this repository.

## Instructions

When this skill is invoked, create comprehensive unit tests for report generation code following these requirements:

### 1. Test Coverage Requirements

**Minimum Coverage**: 80% code coverage for all report generation functions

**Must Test**:
- Data parsing and loading from ndjson files
- Data aggregation and calculation logic
- Metric computation functions
- Report formatting and output generation
- Edge cases and boundary conditions
- Error handling and validation

### 2. Test Structure

Organize tests by report category:
```
tests/
├── test_adoption_metrics.py (or .js/.ts)
├── test_productivity_metrics.py
├── test_feature_usage_metrics.py
├── test_ide_platform_metrics.py
├── test_language_metrics.py
├── test_model_metrics.py
├── test_temporal_metrics.py
├── test_user_segmentation.py
├── test_quality_metrics.py
├── test_cross_dimensional.py
├── test_business_roi_metrics.py
├── test_summary_reports.py
└── test_data_loading.py
```

### 3. Test Categories

#### A. Data Loading Tests
- **Valid data loading**: Verify correct parsing of ndjson files
- **Invalid data handling**: Test malformed JSON, missing fields
- **Empty data sets**: Handle files with zero records
- **Large data sets**: Performance with full 3,490+ records
- **Data validation**: Verify required fields exist

#### B. Metric Calculation Tests
For each metric, test:
- **Correct calculation**: Expected output for known input
- **Zero values**: Handle no activity scenarios
- **Null/undefined handling**: Missing or null field values
- **Division by zero**: Acceptance rates with zero generations
- **Negative values**: Ensure metrics can't go negative when inappropriate
- **Boundary values**: Min/max values, percentiles

#### C. Aggregation Tests
- **Group by operations**: User, day, feature, IDE, language, model
- **Sum aggregations**: Total counts, LOC sums
- **Average calculations**: Mean, median, percentiles
- **Count operations**: Unique users, distinct values
- **Multi-dimensional aggregations**: Cross-tabulations

#### D. Time Series Tests
- **Date range filtering**: Correct date boundaries
- **Daily aggregations**: Proper grouping by day
- **Weekly/monthly rollups**: Correct period calculations
- **Trend calculations**: Growth rates, moving averages
- **Missing dates**: Fill gaps in time series

#### E. Report Output Tests
- **Format validation**: JSON, CSV, HTML output correctness
- **Schema validation**: Output matches expected structure
- **Data completeness**: All required fields present
- **Number formatting**: Proper decimals, percentages, rounding
- **Sort order**: Results sorted correctly

#### F. Integration Tests
- **End-to-end report generation**: Full pipeline from data to output
- **Multiple report types**: Generate all report categories
- **Performance tests**: Generation time under thresholds
- **Memory usage**: No memory leaks with large datasets

### 4. Test Framework Selection

Choose appropriate framework based on implementation language:

**Python**:
```python
import pytest
import pandas as pd
from src.metrics import adoption_metrics

def test_total_active_users():
    # Arrange
    test_data = load_test_fixture('sample_data.json')

    # Act
    result = adoption_metrics.calculate_total_active_users(test_data)

    # Assert
    assert result == 434
    assert isinstance(result, int)
```

**JavaScript/TypeScript**:
```javascript
import { describe, it, expect } from 'vitest';
import { calculateTotalActiveUsers } from '../src/metrics/adoption';

describe('Adoption Metrics', () => {
  it('should calculate total active users correctly', () => {
    // Arrange
    const testData = loadTestFixture('sample_data.json');

    // Act
    const result = calculateTotalActiveUsers(testData);

    // Assert
    expect(result).toBe(434);
    expect(typeof result).toBe('number');
  });
});
```

**Java**:
```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class AdoptionMetricsTest {
    @Test
    void shouldCalculateTotalActiveUsers() {
        // Arrange
        List<CopilotRecord> testData = loadTestFixture("sample_data.json");

        // Act
        int result = AdoptionMetrics.calculateTotalActiveUsers(testData);

        // Assert
        assertEquals(434, result);
    }
}
```

### 5. Test Data Fixtures

Create representative test fixtures:

**Small fixture** (5-10 records): Fast unit tests
```json
[
  {"user_id": 1, "day": "2025-12-12", "user_initiated_interaction_count": 10, ...},
  {"user_id": 2, "day": "2025-12-12", "user_initiated_interaction_count": 5, ...}
]
```

**Medium fixture** (100 records): Integration tests

**Full fixture** (3,490 records): Performance tests

**Edge case fixtures**: Empty arrays, null values, extreme values

### 6. Test Naming Conventions

Use descriptive test names following pattern:
- `test_<function>_<scenario>_<expected_outcome>`

Examples:
- `test_calculate_acceptance_rate_with_zero_generations_returns_zero`
- `test_aggregate_by_user_with_multiple_days_sums_correctly`
- `test_load_ndjson_with_malformed_json_raises_error`

### 7. Assertions to Include

For each test, verify:
- **Correctness**: Result matches expected value
- **Type**: Return type is correct (int, float, dict, list)
- **Shape**: Arrays/lists have expected length
- **Range**: Values within valid ranges
- **Null safety**: No null/undefined in output
- **Immutability**: Input data not modified (if applicable)

### 8. Mock and Stub Guidelines

- **Mock file I/O**: Don't read actual files in unit tests
- **Stub external APIs**: If reports call external services
- **Mock time**: Use fixed dates for reproducible tests
- **Isolate units**: Test functions independently

### 9. Test Execution Requirements

Tests must:
- ✅ Run in isolation (no dependencies between tests)
- ✅ Be deterministic (same input = same output)
- ✅ Be fast (<100ms per unit test)
- ✅ Clean up after themselves (no side effects)
- ✅ Have clear failure messages

### 10. Continuous Integration

Set up test automation:
```yaml
# Example: .github/workflows/test.yml
name: Tests
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run tests
        run: |
          npm test          # or pytest, mvn test, etc.
          npm run coverage  # Generate coverage report
      - name: Check coverage
        run: |
          # Fail if coverage < 80%
```

### 11. Documentation Requirements

Each test file must include:
- Module docstring describing what's tested
- Test class/describe blocks grouped by functionality
- Comments for complex test scenarios
- References to specific metrics from plans/reports.md

### 12. Error Testing Patterns

Test error conditions:
```python
def test_calculate_metric_with_empty_data_raises_value_error():
    with pytest.raises(ValueError, match="Data cannot be empty"):
        calculate_metric([])

def test_load_invalid_json_raises_json_decode_error():
    with pytest.raises(json.JSONDecodeError):
        load_ndjson_file('invalid.json')
```

## Usage

Invoke this skill when:
- Creating new report generation functions
- Modifying existing metric calculations
- Adding new data processing logic
- Before committing report code

## Output

After applying this skill, you should have:
1. ✅ Comprehensive test suite for all report functions
2. ✅ 80%+ code coverage
3. ✅ All tests passing
4. ✅ Test fixtures for various scenarios
5. ✅ Clear test documentation
6. ✅ CI/CD pipeline configured

## Quality Checklist

Before considering tests complete:
- [ ] All metric calculations tested with known inputs/outputs
- [ ] Edge cases covered (empty, null, zero, negative)
- [ ] Data loading tested with valid and invalid data
- [ ] Aggregations tested across all dimensions
- [ ] Time series functions tested with date ranges
- [ ] Report output formats validated
- [ ] Performance tests for large datasets
- [ ] Error handling tested thoroughly
- [ ] Test coverage report generated and reviewed
- [ ] Tests run successfully in CI/CD pipeline

## Resources

- [pytest documentation](https://docs.pytest.org/)
- [Vitest documentation](https://vitest.dev/)
- [JUnit 5 documentation](https://junit.org/junit5/)
- [Test coverage tools](https://coverage.readthedocs.io/)
