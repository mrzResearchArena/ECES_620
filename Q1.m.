% Load the image
image_path = "./Examples/pout.tif";
image_data = imread(image_path);

% Define the gamma value
gamma_value = 0.25;

% Extract dimensions of the image
[num_rows, num_cols] = size(image_data);

% Display the original image
figure;
imshow(image_data);

% Apply gamma correction
image_data_double = double(image_data);
image_data_double = 255 * ((image_data_double / 255) .^ gamma_value);
gamma_corrected_image = uint8(image_data_double);

% Display the gamma-corrected image
figure;
imshow(gamma_corrected_image);

% Display the histogram of the original image
figure;
imhist(image_data);
title_str = sprintf('%s original histogram', image_path);
title(title_str);

% Display the histogram of the gamma-corrected image
figure;
imhist(gamma_corrected_image);
title_str = sprintf('%s %.2f gamma correction histogram', image_path, gamma_value);
title(title_str);

% Define the number of histogram bins
num_bins = 128;

% Perform histogram equalization on the original image
equalized_image = histeq(image_data, num_bins);

% Display the histogram-equalized image
figure;
imshow(equalized_image);
title_str = sprintf('%s original histogram equalization', image_path);
title(title_str);
subtitle_str = sprintf('%d bins', num_bins);
subtitle(subtitle_str);

% Perform histogram equalization on the gamma-corrected image
gamma_corrected_equalized_image = histeq(gamma_corrected_image, num_bins);

% Display the histogram-equalized gamma-corrected image
figure;
imshow(gamma_corrected_equalized_image);
title_str = sprintf('%s %.2f gamma correction histogram equalization', image_path, gamma_value);
title(title_str);
subtitle_str = sprintf('%d bins', num_bins);
subtitle(subtitle_str);

