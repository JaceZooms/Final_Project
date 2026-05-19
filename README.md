Polynomial Fit and Smoother 
The Polynomial Fit and Smoother lets a user load any two-column CSV file, visualize the raw data, and then apply two independent curve-fitting methods side by side: a least-squares polynomial regression and a centered moving-average smoother. Root mean squared error (RMSE) is displayed for each method after every Compute call, giving an immediate quantitative comparison of fit quality. The application is structured so that the UI callbacks delegate all numerical work to two standalone functions in the src/ folder, keeping the UI code clean and making the functions independently testable. 
Known Limitations

High-degree fits (degree ≥ 8) exhibit Runge oscillations near the x endpoints; the app displays the RMSE to help users detect
this but does not auto-select degree.

The moving average RMSE is computed over fewer points than the polynomial RMSE (interior only), so direct comparison
slightly favors the smoother at large windows.

No real-time recompute: changing degree or window requires clicking Compute again.

Only two-column CSV files are supported; files with extra columns are silently truncated to the first two
