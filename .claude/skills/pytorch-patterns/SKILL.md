# PyTorch Patterns Skill

Best practices and patterns for PyTorch development.

## Core Patterns

### Model Definition
- Use `nn.Module` subclassing
- Implement `forward()` method
- Use `@torch.no_grad()` for inference
- Apply `model.eval()` before inference

### Training Loop
```python
model.train()
for batch in dataloader:
    optimizer.zero_grad()
    loss = criterion(model(batch), targets)
    loss.backward()
    optimizer.step()
```

### Memory Optimization
- Use `torch.cuda.empty_cache()` sparingly
- Gradient checkpointing for large models
- Mixed precision with `torch.autocast`
- Delete unused tensors explicitly

### Distributed Training
- `DistributedDataParallel` over `DataParallel`
- Proper process group initialization
- Sync batch norm when needed

### torch.compile (PyTorch 2.0+)
- Use `mode="reduce-overhead"` for small batches
- Use `mode="max-autotune"` for inference
- Handle dynamic shapes with `dynamic=True`

## Common Pitfalls
- Forgetting `.to(device)`
- Not calling `model.eval()` for inference
- Memory leaks from tensor accumulation
- Incorrect gradient handling in custom ops
