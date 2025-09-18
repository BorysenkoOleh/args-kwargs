def mul_clip(*args, **kwargs):
    clip_min = kwargs.get('clip_min', None)
    clip_max = kwargs.get('clip_max', None)

    clipped_args = []
    for num in args:
        if clip_min is not None and num < clip_min:
            num = clip_min
        if clip_max is not None and num > clip_max:
            num = clip_max
        clipped_args.append(num)

    result = 1
    for num in clipped_args:
        result *= num

    return result
print(mul_clip(1,2,3,4))
print(mul_clip(1,2,3,4))
print(mul_clip(2, 100, 3, clip_max=10))
print(mul_clip(2, 3))
print(mul_clip(2, 5, 10, clip_min=4))
print(mul_clip(1, 20, clip_min=5, clip_max=10))
